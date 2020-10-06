---
applicable: SharePoint Online
external help file: PnP.PowerShell.dll-Help.xml
Module Name: PnP.PowerShell
online version: https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnpterm
schema: 2.0.0
title: Get-PnPTerm
---

# Get-PnPTerm

## SYNOPSIS
Returns a taxonomy term

## SYNTAX

### By Term Id
```
Get-PnPTerm
 -Identity <PnP.PowerShell.Commands.Base.PipeBinds.GenericObjectNameIdPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermSet]>
 [-TermStore <PnP.PowerShell.Commands.Base.PipeBinds.GenericObjectNameIdPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermStore]>]
 [-IncludeChildTerms] [-Connection <PnPConnection>] [-Includes <String[]>] [<CommonParameters>]
```

### By Termset
```
Get-PnPTerm
 [-Identity <PnP.PowerShell.Commands.Base.PipeBinds.GenericObjectNameIdPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermSet]>]
 [-TermSet] <PnP.PowerShell.Commands.Base.PipeBinds.TaxonomyItemPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermSet]>
 [-TermGroup] <TermGroupPipeBind>
 [-TermStore <PnP.PowerShell.Commands.Base.PipeBinds.GenericObjectNameIdPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermStore]>]
 [-Recursive] [-IncludeChildTerms] [-Connection <PnPConnection>] [-Includes <String[]>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### EXAMPLE 1
```powershell
Get-PnPTerm -TermSet "Departments" -TermGroup "Corporate"
```

Returns all term in the termset "Departments" which is in the group "Corporate" from the site collection termstore

### EXAMPLE 2
```powershell
Get-PnPTerm -Identity "Finance" -TermSet "Departments" -TermGroup "Corporate"
```

Returns the term named "Finance" in the termset "Departments" from the termgroup called "Corporate" from the site collection termstore

### EXAMPLE 3
```powershell
Get-PnPTerm -Identity ab2af486-e097-4b4a-9444-527b251f1f8d -TermSet "Departments" -TermGroup "Corporate"
```

Returns the term named with the given id, from the "Departments" termset in a term group called "Corporate" from the site collection termstore

### EXAMPLE 4
```powershell
Get-PnPTerm -Identity "Small Finance" -TermSet "Departments" -TermGroup "Corporate" -Recursive
```

Returns the term named "Small Finance", from the "Departments" termset in a term group called "Corporate" from the site collection termstore even if it's a subterm below "Finance"

### EXAMPLE 5
```powershell
$term = Get-PnPTerm -Identity "Small Finance" -TermSet "Departments" -TermGroup "Corporate" -Include Labels
$term.Labels
```

Returns all the localized labels for the term named "Small Finance", from the "Departments" termset in a term group called "Corporate"

## PARAMETERS

### -Connection
Optional connection to be used by the cmdlet. Retrieve the value for this parameter by either specifying -ReturnConnection on Connect-PnPOnline or by executing Get-PnPConnection.

```yaml
Type: PnPConnection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
The Id or Name of a Term

```yaml
Type: PnP.PowerShell.Commands.Base.PipeBinds.GenericObjectNameIdPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermSet]
Parameter Sets: By Term Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: PnP.PowerShell.Commands.Base.PipeBinds.GenericObjectNameIdPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermSet]
Parameter Sets: By Termset
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeChildTerms
Includes the hierarchy of child terms if available

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

### -Recursive
Find the first term recursively matching the label in a term hierarchy.

```yaml
Type: SwitchParameter
Parameter Sets: By Termset
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TermGroup
Name of the termgroup to check.

```yaml
Type: TermGroupPipeBind
Parameter Sets: By Termset
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TermSet
Name of the termset to check.

```yaml
Type: PnP.PowerShell.Commands.Base.PipeBinds.TaxonomyItemPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermSet]
Parameter Sets: By Termset
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TermStore
Term store to check; if not specified the default term store is used.

```yaml
Type: PnP.PowerShell.Commands.Base.PipeBinds.GenericObjectNameIdPipeBind`1[Microsoft.SharePoint.Client.Taxonomy.TermStore]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## RELATED LINKS

[SharePoint Developer Patterns and Practices](https://aka.ms/sppnp)