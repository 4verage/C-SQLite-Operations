# C-SQLite-Operations
Small Library to help easily integrate SQLite into your C# applications. Currently requires the sqlite3.dll file to go into a \dlls\ folder.

Currently only supports SQLite Open / Close / Exec / Errmsg commands. Everything your need to get started using SQLite in C#!

## Requirements
- SQLite.dll (this file)
- sqlite3.dll (get from SQLite)

## How To
1. Place the sqlite3.dll you got from SQLite into a folder in your project called \dlls\

2. In your C# .csproj file add:

        <ItemGroup>
          <Reference Include="dlls/SQLite.dll" />
        </ItemGroup>

## Usage

In your class:  

    using SQLite_Operations;

To open a database file (will create it if it does not exist):  

    SQLite.Open(<filename as string>);

To send a command to SQL (Returns INT):  

    SQLite.Command(<SQL query string>, <IntPtr for error holder>);

To send a query to SQL (Returns a List of Dictionaries (List<Dictionary<string, string?>>)):

    SQLite.Run(<SQL query string>, <IntPtr for error holder>);

To grab an errors that may be thrown:  

     SQLite.Error();
