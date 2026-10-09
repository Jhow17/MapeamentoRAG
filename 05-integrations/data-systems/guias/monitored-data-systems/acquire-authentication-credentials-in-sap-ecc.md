---
title: "Acquire authentication credentials in SAP ECC"
slug: "acquire-authentication-credentials-in-sap-ecc"
updated: 2026-07-31T11:49:49Z
published: 2026-07-31T11:49:49Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-sap-ecc"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in SAP ECC

1. Log in to the SAP ECC Instance and record the following information:
  - **Host** - the name/IP address of the SAP Instance.
  - **User** - your username with the profile that lets you "read" access to Securiti's SAP ECC 6.0 Data system Connector for all the desired objects (tables, views, schemas, and databases).
  - **Password** - your user password.
  - **Client** - the one authenticating the SAP Instance.
  - **System Number** - the number by which target is defined.
  - **Module** - the module that needs scanning (*only the tables related to the selected modules under the SAP module menu are scanned*).
  - **Read Table RFC Name** (optional)

When left blank, default RFC (*Remote Function Call*) is used for the read operation which is limited to 512-byte-per-Row, and scanning for the activated Connector is blocked (only DSRs are supported).

If the name for a custom RFC is provided in the field, it also scans the data source.
  - **Comma Separated Table Names** (optional)

A comma-separated list of Table names. It includes any tables that are missed during the defining of SAP module to Table mappings. You can also input custom-defined tables in the field.

> [!WARNING]
> **Important**
> 
> You must enable port 3300 on the server to let the SAP driver connect to it. Otherwise, you'd get an error message, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(615).png)
2. To create a User in SAP GUI for SAP ECC Instance:
  1. In the type box near the top left, execute **T-code SU01** by clicking on the "green checkmark" as shown below.

![Execute-code_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf89f2df-25e0-0284-f5d1-9ee81dffd9c1.png)
  2. Enter a name in the **User** field, then click on the "create button (page icon)".

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EVG0J2PP.png)
  3. On the following page, select the **Address** tab. Input any details for the new user.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YJZML0SM.png)
  4. Choose the **Logon Data** tab and select **Communications Data** from the "User Type" menu.

Set a password and then confirm it (*this is the same for Connector Activation*).![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WNFLB83H.png)
  5. Click on the **Profiles** tab, then type "SAP_ALL" in the Text Column to assign the profile to the User.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-C3A91ECN.png)
  6. On the toolbar, click the Save icon. A success message is displayed at the bottom status bar "User TEST9 created".

Username is created with correct Permissions.
3. To define the custom Remote Function Call (RFC) Name:
  1. In the SAP Instance, execute **T-code SE37** (*similar to as described above).*
  2. Select **Copy** from the navigation bar, as shown below.
  3. On the **Copy Function Module** dialog, enter **RC_****READ_TABLE** in the **Fr.** **Function** **module** field, and assign a custom read RFC name in the **To Function module**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-10 at 8.49.19 PM.png)

> [!NOTE]
> **Note**
> 
> You can either use an existing or a new Function group.
> 
> In this example, the To Function module is **Z_CUSTOM_READ_TABLE_ONE** and the Function group field is **Z_DAN**.
  4. Click the **Copy** button after you have input respective values in their fields.

A success message is displayed on the bottom status bar "Function module RFC_READ_TABLE copied".
  5. On the following page, enter the name of the custom read RFC name in the **Function** **Module** field, then click **Change**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BA2L3DZ5.png)
  6. Select the **Source code** tab on the **Function Builder** page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-10 at 8.53.46 PM.png)
  7. Replace the existing source code with the source code below.

```plaintext
FUNCTION Z_CUSTOM_READ_TABLE_ONE .
*"----------------------------------------------------------------------
*"*"Local Interface:
*"  IMPORTING
*"     VALUE(QUERY_TABLE) TYPE  DD02L-TABNAME
*"     VALUE(DELIMITER) TYPE  SONV-FLAG DEFAULT SPACE
*"     VALUE(NO_DATA) TYPE  SONV-FLAG DEFAULT SPACE
*"     VALUE(ROWSKIPS) TYPE  SOID-ACCNT DEFAULT 0
*"     VALUE(ROWCOUNT) TYPE  SOID-ACCNT DEFAULT 0
*"     VALUE(FETCHSIZE) TYPE  SOID-ACCNT DEFAULT 50000
*"     VALUE(ORDER_BY) TYPE  CHAR2000 OPTIONAL
*"     VALUE(USE_ET_DATA_4_RETURN) TYPE  SONV-FLAG DEFAULT 'X'
*"  EXPORTING
*"     VALUE(TABLE_ROWS) TYPE  SOID-ACCNT
*"     VALUE(ET_DATA) TYPE  STRING_TABLE
*"  TABLES
*"      OPTIONS STRUCTURE  RFC_DB_OPT
*"      FIELDS STRUCTURE  RFC_DB_FLD
*"      DATA STRUCTURE  CHAR8000
*"  EXCEPTIONS
*"      TABLE_NOT_AVAILABLE
*"      TABLE_WITHOUT_DATA
*"      OPTION_NOT_VALID
*"      FIELD_NOT_VALID
*"      NOT_AUTHORIZED
*"      DATA_BUFFER_EXCEEDED
*"----------------------------------------------------------------------
"
CALL FUNCTION 'VIEW_AUTHORITY_CHECK'
     EXPORTING
          VIEW_ACTION                    = 'S'
          VIEW_NAME                      = QUERY_TABLE
     EXCEPTIONS
          NO_AUTHORITY                   = 2
          NO_CLIENTINDEPENDENT_AUTHORITY = 2
          NO_LINEDEPENDENT_AUTHORITY     = 2
          OTHERS                         = 1.

IF SY-SUBRC = 2.
  RAISE NOT_AUTHORIZED.
ELSEIF SY-SUBRC = 1.
  RAISE TABLE_NOT_AVAILABLE.
ENDIF.

* ----------------------------------------------------------------------
*  If negative ROWCOUNT, return no. of rows in table
* ----------------------------------------------------------------------
IF ROWCOUNT < 0.
  SELECT count(*) FROM (QUERY_TABLE) INTO TABLE_ROWS WHERE (OPTIONS).
  EXIT.
ENDIF.

* ----------------------------------------------------------------------
*  find out about the structure of QUERY_TABLE
* ----------------------------------------------------------------------
DATA BEGIN OF TABLE_STRUCTURE OCCURS 10.
        INCLUDE STRUCTURE DFIES.
DATA END OF TABLE_STRUCTURE.
"DATA TABLE_HEADER LIKE X030L.
DATA TABLE_TYPE TYPE DD02V-TABCLASS.

CALL FUNCTION 'DDIF_FIELDINFO_GET'
  EXPORTING
    TABNAME              = QUERY_TABLE
*   FIELDNAME            = ' '
*   LANGU                = SY-LANGU
*   LFIELDNAME           = ' '
*   ALL_TYPES            = ' '
*   GROUP_NAMES          = ' '
  IMPORTING
*   X030L_WA             =
    DDOBJTYPE            = TABLE_TYPE
*   DFIES_WA             =
*   LINES_DESCR          =
  TABLES
    DFIES_TAB            = TABLE_STRUCTURE
*   FIXED_VALUES         =
  EXCEPTIONS
    NOT_FOUND            = 1
    INTERNAL_ERROR       = 2
    OTHERS               = 3
          .
IF SY-SUBRC <> 0.
  RAISE TABLE_NOT_AVAILABLE.
ENDIF.
IF TABLE_TYPE = 'INTTAB'.
  RAISE TABLE_WITHOUT_DATA.
ENDIF.

* ----------------------------------------------------------------------
*  isolate first field of DATA as output field
*  (i.e. allow for changes to structure DATA!)
* ----------------------------------------------------------------------
DATA LINE_LENGTH TYPE I.
FIELD-SYMBOLS <D>.
ASSIGN COMPONENT 0 OF STRUCTURE DATA TO <D>.
DESCRIBE FIELD <D> LENGTH LINE_LENGTH in character mode.

* ----------------------------------------------------------------------
*  if FIELDS are not specified, read all available fields
* ----------------------------------------------------------------------
DATA NUMBER_OF_FIELDS TYPE I.
DESCRIBE TABLE FIELDS LINES NUMBER_OF_FIELDS.
IF NUMBER_OF_FIELDS = 0.
  LOOP AT TABLE_STRUCTURE.
    MOVE TABLE_STRUCTURE-FIELDNAME TO FIELDS-FIELDNAME.
    APPEND FIELDS.
  ENDLOOP.
ENDIF.

* ----------------------------------------------------------------------
*  for each field which has to be read, copy structure information
*  into tables FIELDS_INT (internal use) and FIELDS (output)
* ----------------------------------------------------------------------
DATA: BEGIN OF FIELDS_INT OCCURS 10,
        FIELDNAME  LIKE TABLE_STRUCTURE-FIELDNAME,
        TYPE       LIKE TABLE_STRUCTURE-INTTYPE,
        DECIMALS   LIKE TABLE_STRUCTURE-DECIMALS,
        LENGTH_SRC LIKE TABLE_STRUCTURE-INTLEN,
        LENGTH_DST LIKE TABLE_STRUCTURE-LENG,
        OFFSET_SRC LIKE TABLE_STRUCTURE-OFFSET,
        OFFSET_DST LIKE TABLE_STRUCTURE-OFFSET,
      END OF FIELDS_INT,
      LINE_CURSOR TYPE I,
      TABLE_STRUCTURE_LENGTH TYPE I,
      TEMPLATE_DATA TYPE char8000.

LINE_CURSOR = 0.
TABLE_STRUCTURE_LENGTH = 0.
CLEAR TEMPLATE_DATA.
*  for each field which has to be read ...
LOOP AT FIELDS.

  READ TABLE TABLE_STRUCTURE WITH KEY FIELDNAME = FIELDS-FIELDNAME.
  IF SY-SUBRC NE 0.
    RAISE FIELD_NOT_VALID.
  ENDIF.

* compute the place for field contents in DATA rows:
* if not first field in row, allow space for delimiter
  IF LINE_CURSOR <> 0 AND DELIMITER NE SPACE AND USE_ET_DATA_4_RETURN EQ SPACE.
    MOVE DELIMITER TO TEMPLATE_DATA+LINE_CURSOR.
    LINE_CURSOR = LINE_CURSOR + STRLEN( DELIMITER ).
  ENDIF.

  IF TABLE_STRUCTURE-OUTPUTLEN > TABLE_STRUCTURE-LENG.
    TABLE_STRUCTURE_LENGTH = TABLE_STRUCTURE-OUTPUTLEN.
  ELSE.
    TABLE_STRUCTURE_LENGTH = TABLE_STRUCTURE-LENG.
  ENDIF.

* ... copy structure information into tables FIELDS_INT
* (which is used internally during SELECT) ...
  FIELDS_INT-FIELDNAME  = TABLE_STRUCTURE-FIELDNAME.
  FIELDS_INT-LENGTH_SRC = TABLE_STRUCTURE-INTLEN.
  FIELDS_INT-LENGTH_DST = TABLE_STRUCTURE_LENGTH.
  FIELDS_INT-OFFSET_SRC = TABLE_STRUCTURE-OFFSET.
  FIELDS_INT-OFFSET_DST = LINE_CURSOR.
  FIELDS_INT-TYPE       = TABLE_STRUCTURE-INTTYPE.
  FIELDS_INT-DECIMALS   = TABLE_STRUCTURE-DECIMALS.
* compute the place for contents of next field in DATA rows
  LINE_CURSOR = LINE_CURSOR + TABLE_STRUCTURE_LENGTH.
  IF LINE_CURSOR > LINE_LENGTH AND NO_DATA EQ SPACE AND USE_ET_DATA_4_RETURN EQ SPACE.
    RAISE DATA_BUFFER_EXCEEDED.
  ENDIF.
  APPEND FIELDS_INT.

* ... and into table FIELDS (which is output to the caller)
  FIELDS-FIELDTEXT = TABLE_STRUCTURE-FIELDTEXT.
  FIELDS-TYPE      = TABLE_STRUCTURE-INTTYPE.
  FIELDS-LENGTH    = FIELDS_INT-LENGTH_DST.
  FIELDS-OFFSET    = FIELDS_INT-OFFSET_DST.
  MODIFY FIELDS.

ENDLOOP.
* end of loop at FIELDS

* ----------------------------------------------------------------------
*  read data from the database and copy relevant portions into DATA
* ----------------------------------------------------------------------
* output data only if NO_DATA equals space (otherwise the structure
* information in FIELDS is the only result of the module)
IF NO_DATA EQ SPACE.

DATA: tab_ref TYPE REF TO data,
      ld_buf type c length 255,
      ls_out type string,
      lv_str TYPE string,
      first_col type i,
      index TYPE i,
      db_cursor TYPE CURSOR,
      lv_orderby TYPE string.
FIELD-SYMBOLS: <WA> TYPE STANDARD TABLE,
               <lt_temp> TYPE STANDARD TABLE,
               <fs_comp> TYPE ANY,
               <WA_LINE> TYPE ANY,
               <data_line> LIKE LINE OF DATA.

CREATE DATA tab_ref TYPE STANDARD TABLE OF (QUERY_TABLE).
ASSIGN  tab_ref->* TO <WA>.

 IF ROWCOUNT > 0.
   ROWCOUNT = ROWCOUNT + ROWSKIPS.
 ENDIF.

 IF ORDER_BY IS INITIAL.
   OPEN CURSOR db_cursor FOR
   SELECT * FROM (QUERY_TABLE) UP TO ROWCOUNT ROWS WHERE (OPTIONS).
 ELSE.

   lv_orderby = ORDER_BY.
   REPLACE ALL OCCURRENCES OF ',' IN lv_orderby WITH | |.
   CONDENSE lv_orderby.

   OPEN CURSOR db_cursor FOR
   SELECT * FROM (QUERY_TABLE) UP TO ROWCOUNT ROWS WHERE (OPTIONS) ORDER BY (lv_orderby).
 ENDIF.

 WHILE 1 = 1.
   FETCH NEXT CURSOR db_cursor INTO TABLE <WA> PACKAGE SIZE FETCHSIZE.
   IF SY-DBCNT <= 0 OR SY-SUBRC <> 0.
     CLOSE CURSOR db_cursor.
     EXIT.
   ENDIF.

   IF SY-DBCNT <= ROWSKIPS.
     index = SY-DBCNT.
     CONTINUE.
   ELSEIF index < ROWSKIPS.
     DELETE <WA> FROM 1 TO ROWSKIPS - index.
     index = SY-DBCNT.
   ENDIF.

   IF USE_ET_DATA_4_RETURN EQ SPACE.
*   copy all relevant fields into DATA (output) table
     LOOP AT <WA> ASSIGNING <WA_LINE>.
       DATA = TEMPLATE_DATA.
       ASSIGN DATA TO <data_line>.
       LOOP AT FIELDS_INT.
         IF FIELDS_INT-TYPE = 'P'.
           ASSIGN COMPONENT FIELDS_INT-FIELDNAME OF STRUCTURE <WA_LINE> TO <fs_comp>
           TYPE 'P'
           DECIMALS FIELDS_INT-DECIMALS.
        ELSE.
          ASSIGN COMPONENT FIELDS_INT-FIELDNAME OF STRUCTURE <WA_LINE> TO <fs_comp>.
       ENDIF.
       IF sy-subrc <> 0.
         CONTINUE.
       ENDIF.
         <data_line>+FIELDS_INT-OFFSET_DST(FIELDS_INT-LENGTH_DST) = <fs_comp>.
       ENDLOOP.
*   end of loop at FIELDS_INT
       APPEND DATA.
     ENDLOOP.
   ELSE.
*   copy all relevant fields into ET_DATA (output) table
     LOOP AT <WA> ASSIGNING <WA_LINE>.
       CLEAR ls_out.
       first_col = 1.
       LOOP AT FIELDS_INT.
         ASSIGN COMPONENT FIELDS_INT-FIELDNAME OF STRUCTURE <WA_LINE> TO <fs_comp>.
         IF sy-subrc <> 0.
           CONTINUE.
         ENDIF.
         CASE FIELDS_INT-TYPE.
           WHEN 'D'.  " DATE TYPE
             lv_str = <fs_comp> && ''.
           WHEN 'T'.  " TIME TYPE
             lv_str = <fs_comp> && ''.
           WHEN 'P' OR 'N' OR 'a' OR 'e' OR 'b' OR 's' OR '8'.  " NUMERIC TYPE
             WRITE <fs_comp> TO ld_buf LEFT-JUSTIFIED.
             lv_str = ld_buf.
           WHEN OTHERS.  " CAHRCTER TYPE
             lv_str = <fs_comp> && ''.
         ENDCASE.
         IF first_col = 1.
           ls_out = lv_str.
           first_col = 0.
         ELSE.
           CONCATENATE ls_out lv_str INTO ls_out SEPARATED BY DELIMITER.
         ENDIF.
       ENDLOOP.
       APPEND ls_out TO ET_DATA.
     ENDLOOP.
   ENDIF.
 ENDWHILE.
ENDIF.

ENDFUNCTION.
```
4. 
  1. On the **Export** tab, enter the following parameters

| Parameter Name | Typing | Associated Type | Pass value |
| --- | --- | --- | --- |
| `TABLE_ROWS` | `TYPE` | `SOID-ACCNT` | mark the checkbox for Pass value |
| `ET_Data` | `TYPE` | `STRING_TABLE` | mark the checkbox for Pass value |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-10 at 9.08.53 PM.png)
  2. Then click **Save (floppy disk icon)** on the navigation bar.
  3. On the same page, select the **Tables** tab.
  4. Replace “TAB512” with **CHAR8000** in the **Associated Type** Column for the ***DATA*** parameter, and click "Save (floppy disk icon)".

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-10 at 8.56.20 PM.png)
  5. On the same page, select the **Import** tab, and parameters will be shown as mentioned below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VMJZNGXJ.png)
  6. Click the **Activate** icon on the navigation bar.

> [!NOTE]
> Note
> 
> Before activating the RFC function, you can verify the syntax. To do this, you either press `F2` or click on the highlighted icon, as shown below:
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-10 at 8.58.33 PM.png)
  7. The new custom RFC is now activated and displays the **Object(s)** **activated** message on the bottom status bar, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-10 at 9.04.48 PM.png)
5. Proceed to [Connecting the SAP ECC with Securiti](/latest/docs/connecting-the-sap-ecc-with-securiti).
