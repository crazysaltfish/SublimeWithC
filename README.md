# SublimeWithC
deploy C++ builder for sublime
*************
use the following code to create a new sublime build system.
*************
{
    // "shell_cmd": "make"
    "encoding": "utf-8",
    "working_dir": "$file_path",
    "shell_cmd": "g++ -Wall -std=c++0x \"$file_name\" -o \"$file_base_name\"",
    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
    "selector": "source.cpp",

    "variants": 
    [
        {   
        "name": "Run",
            "shell_cmd": "g++ -Wall -std=c++0x  \"$file\" -o \"$file_base_name\" && \"${file_path}/${file_base_name}\""
        },
        {   
        "name": "RunInCmd",
            "shell_cmd": "g++ -Wall -std=c++0x  \"$file\" -o \"$file_base_name\" && start cmd /c \"\"${file_path}/${file_base_name}\" & pause \""
        }
    ]
}
