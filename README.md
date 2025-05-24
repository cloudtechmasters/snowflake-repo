# snowflake-repo
#SELECT * FROM TABLE(LIST(@A1SF_EXTSTAGE_101_676/Adlucent/)) ORDER BY last_modified DESC;


✅ Option 2: Without block (standalone SELECT)
If you just want to test it quickly:


SELECT 'Adlucent/Adlucent_Index_Feed_' || TO_CHAR(CURRENT_DATE, 'YYYYMMDD') || '.txt.gz' AS file_name;
This is ideal for debugging the dynamic filename string before using it in the COPY INTO command.
