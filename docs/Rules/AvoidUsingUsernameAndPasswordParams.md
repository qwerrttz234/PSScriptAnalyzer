# AvoidUsingUsernameAndPasswordParams

**Severity Level: Error**

## Description

To standardize command parameters, credentials should be accepted as objects of type
**PSCredential**. Functions should not make use of username or password parameters.

## How

Change the parameter to type **PSCredential**.

## Example

### Wrong

```powershell
function Test-Script
{
    [CmdletBinding()]
    Param
    (
        [String]
        $Username,
        [SecureString]
        $Password
    )
    ...
}
```

### Correct

```powershell
function Test-Script
{
    [CmdletBinding()]
    Param
    (
        [PSCredential]
        $Credential
    )
    ...
}
```