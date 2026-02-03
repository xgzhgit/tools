# Edit MacromatiX Report Standard Parameters

A Visual Studio extension to apply standard parameters and styles to MacromatiX RDL reports.

## Supported report versions
- http://schemas.microsoft.com/sqlserver/reporting/2008/01/reportdefinition
- http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition
- http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition

## Supported Visual Studio
- Microsoft Visual Studio 17+ (2022)

## Configuration

### Setting Workspace to Local Directory

By default, the extension stores settings files in the user's AppData folder. To use a local directory as your workspace:

1. **Option 1: Using Environment Variables**
   - Set the `MACROMATIX_WORKSPACE` environment variable to your desired local directory path
   - Example (Windows): `C:\MyProjects\ReportSettings`
   - Example (Unix-style): `/home/user/projects/ReportSettings`
   - The extension will use this directory for storing all settings files

2. **Option 2: Using Configuration File**
   - Create a `macromatix.config` file in your project root directory
   - Add the workspace path configuration:
     ```xml
     <configuration>
       <workspace>/path/to/your/workspace</workspace>
     </configuration>
     ```
   - Replace `/path/to/your/workspace` with your actual directory path
   - The extension will automatically detect and use this configuration

3. **Option 3: Project-Relative Path**
   - Place a `.macromatix` folder in your project root directory
   - The extension will automatically use this folder as the workspace
   - This is useful for team collaboration as settings can be version-controlled

### Settings File Location

The extension stores the following files in the configured workspace directory:
- `StandardParameters.xml` - Standard parameter definitions
- `ReportStyles.xml` - Report style configurations
- `Settings.json` - General extension settings

If no custom workspace is configured, files are stored in:
- `%APPDATA%\MacromatiX\ReportStandardParameters\`

## How to use
After installation, three menu items are added to the Tools menu:
- Apply Standard Parameters
- Edit Standard Parameters
- Edit Report Style

### Edit Standard Parameters
Edit the report's standard parameters. The dialog shows the default items for the current report standard. You can add, delete, or modify entries; changes are saved to a persistent settings file.

### Edit Report Style
View and edit the report standard style values and supported formats. Double-click a value to edit it, then use Save to persist changes to the settings file.

### Apply Standard Parameters
This command is available only when the active document is an RDL report. It performs the following steps:

1. Verify the report version is supported.
2. Inspect table header row counts.
3. Ensure standard parameters exist in the report; add any that are missing.
4. Set standard parameter layouts.
5. Apply report header styles.
6. Apply report grid styles.

> ⚠️ WARNING:
> The table header inspection will display all rows where the parameter value count accounts for more than 60%. However, the report header application only supports header rows starting from the first row.
>  Therefore, if any row marked as a header appears within the grid’s content area, modify the header row settings in the "Confirm Table Header Rows" dialog to use header rows starting from the first row.