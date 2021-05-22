## Getting list of programs installed from command line
This is extremely useful when you are swapping your machine or doing a clean install and you need a list of programs you have installed.

Windows comes with a tool called `wmic`.

### Windows Management Instrumentation Command-line (WMIC)

This is a command-line and scripting interface that simplifies the use of Windows Management Instrumentation (WMI) and systems managed through WMI.

WMIC is based on aliases. Aliases make the primary data provided by WMI available without having to understand WMI-specific concepts. WMI data and many WMI features are also accessible through WMI without aliases.

For more information: [WMIC documentation](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/wmic.mspx?mfr=true)

The first thing we need to do is open a command Prompt.

1. Click Start and type CMD in the search box.
2. Click cmd.exe at the top of the search results.
3. At the cmd prompt type wmic and hit enter.
4. You will now see `wmic:root\cli>`
5. Type product get name,version hit enter.
    `wmic:root\cli>product get name,version`

If you want to export the list to a text file
`wmic:root\cli>/output:c:\ProgramList.txt product get name,version`

You may not get the list of all the applications here. 
Reason explained [here](http://stackoverflow.com/questions/673233/wmi-installed-query-different-from-add-remove-programs-list)