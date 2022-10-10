
## Get info about O/S
`sysinfo`

## Find
List all files in C root
`Get-Childitem –Path C:\`
`Get-Childitem –Path C:\ -Recurse`
`Get-Childitem –Path C:\ -Include *HSG* -File -Recurse -ErrorAction SilentlyContinue`
`Get-Childitem –Path C:\ -Include *HSG* -Exclude *.JPG,*.MP3,*.TMP -File -Recurse -ErrorAction SilentlyContinue`
`Get-ChildItem -Path C:\ -Include *.doc,*.docx -File -Recurse -ErrorAction SilentlyContinue | Where-Object { $_.LastWriteTime -ge $FindDate -and $_.LastWriteTime -le $Finddate.adddays(1) }`

## Env var
`$Env:Foo = 'An example'`