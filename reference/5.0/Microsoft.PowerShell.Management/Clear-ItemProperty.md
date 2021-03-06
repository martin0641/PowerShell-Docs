---
description:  
manager:  carmonm
ms.topic:  reference
author:  jpjofre
ms.prod:  powershell
keywords:  powershell,cmdlet
ms.date:  2016-12-12
title:  Clear ItemProperty
ms.technology:  powershell
schema:   2.0.0
online version:   http://go.microsoft.com/fwlink/?LinkId=821570
external help file:   Microsoft.PowerShell.Commands.Management.dll-Help.xml
---


# Clear-ItemProperty

## SYNOPSIS
Clears the value of a property but does not delete the property.

## SYNTAX

### Path (Default)
```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### LiteralPath
```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-ItemProperty** cmdlet clears the value of a property, but it does not delete the property.
You can use this cmdlet to delete the data from a registry value.

## EXAMPLES

### Example 1: Clear the value of registry key
```
PS C:\> Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

This command clear the data in the Options registry value in the MyApp subkey of HKEY_LOCAL_MACHINE\Software\MyCompany.

Because the command is being issued from a file system drive (C:), it uses the fully qualified path to the HKLM: drive and the Software\MyCompany\MyApp subkey.
It uses the *Name* parameter to specify the Options value.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude
Specifies, as a string array, an item or items that this cmdlet excludes.
The value of this parameter qualifies the *Path* parameter.
Enter a path element or pattern, such as *.txt or s*.
Wildcards are permitted.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Specifies a filter in the provider's format or language.
The value of this parameter qualifies the *Path* parameter.
The syntax of the filter, including the use of wildcards, depends on the provider.
Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having Windows PowerShell filter the objects after they are retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.
Implementation varies from provider to provider.
For more information, see about_Providers.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include
Specifies, as a string array, an item or items that this cmdlet clears.
The value of this parameter qualifies the *Path* parameter.
Enter a path element or pattern, such as *.txt.
Wildcards are permitted.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath
Specifies the path to the property being cleared.
Unlike the *Path* parameter, the value of *LiteralPath* is used exactly as it is typed.
No characters are interpreted as wildcards.
If the path includes escape characters, enclose it in single quotation marks.
Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.

```yaml
Type: String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the property to be cleared, such as the name of a registry value.
Wildcards are not permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to the property being cleared.
Wildcards are permitted.

```yaml
Type: String[]
Parameter Sets: Path
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseTransaction
Includes the command in the active transaction.
This parameter is valid only when a transaction is in progress.
For more information, see about_Transactions.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a path string to this cmdlet.

## OUTPUTS

### None or System.Management.Automation.PSCustomObject
When you use the *PassThru* parameter, **Clear-ItemProperty** generates a **PSCustomObject** object that represents the cleared item property.
Otherwise, this cmdlet does not generate any output.

## NOTES
* You can use **Clear-ItemProperty** to delete the data in registry values without deleting the value. If the data type of the value is Binary or DWORD, clearing the data sets the value to zero. Otherwise, the value is empty.

  You can also refer to **Clear-ItemProperty** by its built-in alias, clp.
For more information, see about_Aliases.

  The **Clear-ItemProperty** cmdlet is designed to work with the data exposed by any provider.
To list the providers available in your session, type `Get-PSProvider`.
For more information, see about_Providers.

*

## RELATED LINKS

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)


