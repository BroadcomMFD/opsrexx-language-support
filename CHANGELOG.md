# Change Log

All notable changes to the "OPS/REXX Language Support" extension will be documented in this file.

## `0.6.3` (2025-01-28)

- bug fix for ARM rule auto-recognition
- Updates dependencies to maintain technical currency
  
## `0.6.2` (2024-12-16)

- bug fix

## `0.6.1` (2024-12-11)

- Updates README file association instructions
- adds first line check for `/* OPSREXX */` syntax

## `0.6.0` (2024-11-22)

- Adds the ability to issue the following commands via the OPS/MVS REST API with [@broadcom/ops-for-zowe-cli](https://www.npmjs.com/package/@broadcom/ops-for-zowe-cli):
    - `Execute Program`
    - `Execute Program with Parameters` (keyboard shortcut `Ctrl+Shift+E`)
- Adds dynamic finding of rule set to all previous rule commands:
    - `View Rule Status`
    - `Enable Rule`
    - `Disable Rule`
    
    Rule commands no longer require a default rule set to be used.
- Removes the user settings:
    - `Connection Options: Rule Set`
    - `Connection Options: Rest Api`
- Adds the user settings:
    - `Program Output Channel: Auto-Open`
    - `Execute Program Default: Wait`
    - `Execute Program Default: Max Queue`
    - `Execute Program Default: Workspace`
    - `Execute Program Default: Timeout`
    - `Execute Program Default: Output Limit`
- Modifies Command Menu Interface to include submenus for Program and Rule command groups
- Updates dependencies to maintain technical currency
- Updates README with new instructional GIFS 

## `0.5.4` (2024-10-10)

- Enhances documentation for Address Host Environments

## `0.5.3` (2024-10-02)

- Patch for Zowe Explorer V3 IntelliSense support

## `0.5.2` (2024-10-01)

- Adds formatted compilation error messages for failed commands (View, Enable, or Disable)
- Updates OPS/REXX built-in functions and host environment documentation for currency
- Adds dynamic insertion of variable arguments to all OPS/REXX built-in functions and host environments
- Updates dependencies to maintain technical currency
- Adds Zowe V3 Conformance

## `0.5.1` (2024-08-09)

- Adds 36 new syntax error checks (thanks @dd066068)
- Adds snippets for all rule types
- Adds Favicons (file icons) for OPSREXX file types
- Adds new error messages
- Fixes hover help bugs

## `0.5.0` (2024-07-19)

- Adds new extension setting for using an OPS/MVS REST API connection

- Adds the ability to issue the following commands via the OPS/MVS REST API with [@broadcom/ops-for-zowe-cli](https://www.npmjs.com/package/@broadcom/ops-for-zowe-cli):
    - `View Rule Status`
    - `Enable Rule`
    - `Disable Rule`
    
   The commands can be issued using local `.opsrexx` files or rules opened in Zowe Explorer.
   
- Adds all remaining AOF stem variables for SEC rule types

- Adds autocompletion of `DO END` and `IF THEN` statements

- Enhances existing embedded documentation for OPS/MVS functions and host environments

- Adds documentation for `View Rule Status`, `Enable Rule`, and `Disable Rule` commands

## `0.4.2` (2024-06-05)

- Remediates CVE: [2024-4068](https://nvd.nist.gov/vuln/detail/CVE-2024-4068)

## `0.4.1` (2024-04-03)

- Updates dependencies for currency

## `0.4.0` (2024-02-28)

- Adds support for IntelliSense autocompletion and hover definition provider for all AOF Stem Variables
- Updates readme for release
- Addresses all known security and operational risks


## `0.3.0` (2023-10-18)

- Adds support for IntelliSense autocompletion and hover definition provider for:
  - All prior supported OPS/REXX built-in functions and host environments
  - AOF stem variables:
    - Command Rules: `CMD.TEXT`, `CMD.USER`, and `CMD.USERID`
    - Security Rules: `SEC.OPAUJBNA`, `SEC.OPAUUSID`, and `SEC.OPAURQTX`
    - Message Rules: `MSG.ID`, `MSG.TEXT`, and `MSG.JOBNAME`
- Provides instructions for `files.associations` setting configuration in README
- Provided documentation for `View Rule Status` command


## `0.2.0` (2023-09-13)

- Adds support for OPS/REXX built-in functions:
  - DATE, FIND, INDEX, OPSACTN, OPSACTFN, OPSAPI, OPSARM, OPSARMST, OPSBITS, OPSBN, OPSCA7, OPSCAWTO, OPSCLEDQ, OPSCPF, OPSCPU, OPSDELV,OPSDEV, OPSDUMP, OPSECURE, OPSENQ, OPSGETVL, OPSHFI, OPSIPL, OPSJESX, OPSLIKE, OPSLOG, OPSLOGMG, OPSPDS, OPSPRM, OPSPRMLB, OPSSEND, OPSSETV, OPSSMF, OPSSMTBL, OPSSRM, OPSTATUS, OPSTHRSH, OPSTORE, OPSUBMIT, OPSUSS, OPSVALUE, OPSVASRV, OPSVSAM, OPSWAIT, OPSWLM, OPSWORD, OPSYSPLX, OPSYSSYM, TIME, and TRACE
- Adds support for OPS/REXX Host Environments:
  - AC, AP, EPI, ESP, HWS, MIM, MQ, OPSCTL, OSF, OSFTSL, OSFTSP, SERVDESK, and SQL
- Adds support for AOF Rule Types: 
  - DOM, EOS, GLV, REQ, SCR, SEC, TLM, and USS
- Corrects syntax highlighting for multi-line strings and comments
- Adds use of `@zowe/secrets-for-zowe-sdk` package to replace non-supported `keytar` package functions

## `0.1.2` (2023-07-21)

- Adds ADDRESS OPER support
- Adds ADDRESS AOF support
- Enables configurable log level

## `0.1.1` (2023-07-12)

- Corrects failure on hover on LF (instead of CRLF)
- Disables comment pair checking which fails when adjacent to sequence numbers

## `0.1.0`

- Initial release to Broadcom Validate
