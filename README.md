[![GitHub issues](https://img.shields.io/github/issues-raw/BroadcomMFD/opsrexx-language-support)](https://github.com/BroadcomMFD/opsrexx-language-support/issues) [![license](https://img.shields.io/badge/license-Broadcom-green)](/LICENSE)

# OPS/REXX Language Support 


The OPS/REXX language is a crucial part of the Broadcom OPS/MVS® product that adds to standard REXX a set of extensions to automate and enhance the productivity of z/OS operations. With the OPS/REXX Language Support extension, automation engineers can develop OPS/MVS Automated Operations Facility (AOF) rules more efficiently by editing OPS/REXX in a local VS Code environment.

## Key Features
OPS/REXX Language Support brings the following advantages to AOF rule development:

- Syntax highlighting in OPS/REXX to help you distinguish the elements of AOF rules 
- Autocompletion of OPS/REXX built-in functions, host environment names, and AOF event variable names 
- Hover help for OPS/REXX built-in functions, host environment names, and AOF event variable names
- Basic error checking for AOF rule syntax
- Access to a library of useful OPS/REXX rule snippets

The OPS/REXX Language Support extension does _not_ provide the ability for you to download from, upload to, or submit jobs on the mainframe. To access mainframe code while using OPS/REXX Language Support, we recommend Zowe Explorer (see [Recommended Software](#recommended-software)) or Zowe CLI.

## Recommended Software
The OPS/REXX Language Support extension has no prerequisite software. However, for your best experience with OPS/REXX Language Support, we recommend the following software.

### REXX Language Support Extension
For correct display of syntax highlighting, we recommend using OPS/REXX Language Support with a REXX language support extension. OPS/REXX Language Support has been tested for compatibility with the [Broadcom REXX Language Support extension](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.lsp-for-rexx).

### Zowe Explorer
We recommend using Zowe Explorer to access mainframe code while using OPS/REXX Language Support. For more information about the Zowe Explorer extension, see [Zowe Explorer](https://marketplace.visualstudio.com/items?itemName=Zowe.vscode-extension-for-zowe) on the VS Code marketplace.

<img src='https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/zowe-conformant-zowev2-explorer.png' width='20%' height='20%' alt='This extension is conformant with Zowe Explorer v2'>

## Using OPS/REXX Language Support with OPS/MVS
Although it is possible to use the OPS/REXX Language Support extension without access to OPS/MVS, most users will want to use the extension while interacting with an OPS/MVS instance.  To use the OPS/REXX Language Support extension with OPS/MVS, you will need:

- An instance of OPS/MVS with the Web Services component installed.
    
    - When you have multiple instances of OPS/MVS running on a single system, only one Web Services component is required. A single OPS/MVS Web Services component can access all OPS/MVS instances on a single system.
    
  - If you are using multiple OPS/MVS instances running on different systems, install and configure the Web Services component to an OPS/MVS instance on each system. One Web Services component is required for each system.   
- For OPS/MVS release 13.5 only, PTFs SO06379 and SO06380 must be applied.

- When working on OPS/REXX files, always make sure the file type is **.opsrexx** to ensure extension features are automatically enabled. For more information, see [Configuring for Zowe Explorer](#configuring-for-zowe-explorer-recommended).

### Security
- To issue commands from the OPS/REXX Language Support extension to OPS/MVS instances, you must be granted access to OPS/MVS resources AOF, SQL, OPSSMTBL, and OPSGLOBAL through OPS/MVS Security.

- [Use Zowe Explorer](https://docs.zowe.org/stable/user-guide/ze-profiles) to create a team configuration file containing the connection information for the OPS/MVS instance you would like to connect to. Provide the following information:
    - The host name of the LPAR on which OPS/MVS Web Services is running.
    - The OPS/MVS Web Services port number.
    - A user name that has authority to access OPS/MVS Web Services.
    - The password to the account tied to the user name.
- Alternatively, you can follow [these steps](https://techdocs.broadcom.com/us/en/ca-mainframe-software/devops/ca-brightside/4-0/using/zowe-cli/available-cli-plug-ins/ca-ops-mvs-plug-in-for-zowe-cli.html) to manually create your team configuration file.
   
## Configuring for Zowe Explorer (Recommended)
To ensure that data sets accessed through Zowe Explorer are recognized by the extension as **.opsrexx** files, you must create a file association in your VS Code settings.

To create a file association, use one of the two following options.

**Option 1: Create a file association in Workspace Settings**     
1. Use the command palette in VS Code (`Ctrl/Cmd + Shift + P`) to locate the Workspace Settings.
2. Scroll down to the **Files: Associations** setting and click **Add Item**.
3. Add `*.REXX(*` to the `Key` field, and `opsrexx` to the `Value` field.
4. Add `*.RULES(*` to the `Key` field, and `opsrexx` to the `Value` field.

**Option 2: Create a file association in User Settings**
1. Use the command palette in VS Code (`Ctrl/Cmd + Shift + P`) to locate the file **settings.json** (User Settings).
2. In **settings.json**, add the lines `"*.REXX(*": "opsrexx"` and `"*.RULES(*": "opsrexx"` under `"files.associations"` as shown in the following example:
  
      ```
          "files.associations": {
              "*.REXX(*": "opsrexx",
              "*.RULES(*": "opsrexx",
          },
      ``` 

After completing the steps for either of the two options, you can use Zowe Explorer to access **.opsrexx** files.

## Using OPS/REXX Language Support

### OPS/REXX Syntax Highlighting
Use OPS/REXX syntax highlighting and symbol resolution to help you avoid syntax errors when developing rules.

![Syntax highlighting](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/syntax-highlighting.PNG)

### OPS/REXX Hover Insights
Place and hold your cursor over an OPS/REXX element to view more information about it. Hover insights are available for OPS/REXX built-in functions, host environments, or AOF event variable names.

![Hover Insights](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/gifs/hover.gif)

### Variable Autocompletion
To trigger autocompletion of AOF variables, type the `.` character after an AOF rule type stem, such as `msg.`. 
AOF variable completions are supported for all rule types. 

![AOF Variable Completion](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/gifs/stem-var-completion.gif)

Variable autocompletion is triggered automatically when you type an OPS/REXX built-in function or host environment name.

![Function and Host Env Completion](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/gifs/basic-completion.gif)

### Syntax error checking
The OPS/REXX Language Support extension automatically performs some basic error checks on AOF rule syntax, such as the line length warning shown in the following image.

![Syntax Error Checking](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/line-too-long-error.PNG)

### Use the `OPS/MVS: Show Rule Status` command
This feature requires an OPS/MVS connection and Zowe Explorer.

To use the `OPS/MVS: Show Rule Status` command:
1. Open the command palette by pressing `Ctrl/Cmd + Shift + P`.
2. Type in and select `OPS/MVS: Show Rule Status`. 

A request will be sent to your configured OPS `subsystem` and `ruleset` using the name of the currently open file as the rule whose status is being checked. The VS Code window will pop up with a status of `ENABLED`, `DISABLED`, or `NOT FOUND`, or an error message.

![OPS/MVS: Show Rule Status](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/gifs/rule-status-cmd.gif)

### Use OPS/REXX Snippets
Before you write AOF rules from scratch, check the snippet library for any applicable rule snippets.
To use the snippet library:

1. Open the VS Code command palette by pressing `Ctrl/Cmd + Shift + P`.
2. Type `Insert Snippet`.
3. Click the command or press Enter.
4. Choose the type of rule snippet you want to insert.
5. Fill in the templated values to complete the OPS/REXX rule.

![Snippets](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/gifs/function-cmd.gif)


For a quicker way to access the snippets:

1. Begin typing the name of a snippet (such as `)MSG`) in the editor.
 
   VS Code autocomplete suggests the full name of the snippet.
 
2. Select the suggested snippet and press Enter.

![Snippets](https://github.com/BroadcomMFD/opsrexx-language-support/blob/main/docs/images/gifs/snippet.gif)

 Using snippets promotes consistent and correct syntax in the rules you design.  
 
 ------------------------------------------------------------------------------------------------
Copyright © 2024 Broadcom. The term "Broadcom" refers to Broadcom Inc. and/or its subsidiaries.
