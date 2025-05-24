# snowflake-repo
✅ Option 1: Just test dynamic filename with SELECT block

DECLARE
  file_name STRING;
BEGIN
  -- Dynamically generate file name
  SELECT 'Adlucent/Adlucent_Index_Feed_' || TO_CHAR(CURRENT_DATE, 'YYYYMMDD') || '.txt.gz'
    INTO file_name;

  -- Return it as result
  RETURN TABLE (SELECT file_name);
END;
✅ This will return something like:
Adlucent/Adlucent_Index_Feed_20250614.txt.gz

✅ Option 2: Without block (standalone SELECT)
If you just want to test it quickly:


SELECT 'Adlucent/Adlucent_Index_Feed_' || TO_CHAR(CURRENT_DATE, 'YYYYMMDD') || '.txt.gz' AS file_name;
This is ideal for debugging the dynamic filename string before using it in the COPY INTO command.
