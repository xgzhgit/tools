# Set Connection
Use Tools > `Set Connection` to configure the Microsoft SQL Server connection used by the SQL formatting features.
### Steps
1.	In Visual Studio, open Tools > Set Connection.
2.	Enter or update the required connection details:
  +	Server
  +	Database
  +	Authentication
  +	Username
  +	Password
  +	Connection Timeout
  +	Command Timeout
  +	Encrypt
  +	Trust Server Certificate
 3.	Click OK to save the configuration.
###  Notes

+	Server and Database are required.
+	If SQL authentication is selected, Username is also required.
+	If Windows authentication is selected, Username and Password are disabled.
---

# Apply SQL Complete
Use Tools > Apply SQL Complete to automatically format and standardize the SQL in the currently active .sql file.
What this command does

## The command applies the project’s SQL review standards, including:
1.	Automatically inserts WITH (NOLOCK) for eligible table references.
2.	Converts T-SQL keywords to uppercase.
3.	Adds explicit AS for renamed expressions in SELECT lists.
4.	Adds schema names to unqualified tables and views when metadata can resolve them.
5.	Loads schema and object metadata dynamically from SQL Server.

   
### Steps
1.	Open the .sql file to update.
2.	In Visual Studio, click Tools > Apply SQL Complete.
3.	The command reads the content of the active file.
4.	The SQL is reformatted and written back to the same active editor.

   
### Notes
+	This command updates the content in the active editor only.
+	The file is not saved automatically after formatting.
+	Save the file manually if the result is correct.
---
Summary
+	Use Tools > Set Connection to configure the SQL Server connection.
+	Use Tools > Apply SQL Complete to apply SQL formatting and review standards to the current SQL file.
+	After applying formatting, review the changes and save the file manually.
If needed, this can also be rewritten as a README.md style document for the repository.
