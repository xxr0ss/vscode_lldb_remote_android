# Usage

* (Optional) set `PYTHONPATH` in `.env` so that you can import lldb when writting python scripts

* Install VS Code plugin `Tasks Shell Input` by Augusto

* Specify how your lldb connect to remote-android before attaching to target process in `.vscode/launch.json`:
    ```json
    {
        "configurations": [
            {
                // ...
                "initCommands": [
                    "platform select remote-android",

                    "platform connect connect://<Device ID>:6666", // You can use `adb devices` to get that
                    // "platform connect connect://localhost:6666", // you need to run `adb forward tcp:6666 tcp:6666`
                    // "platform connect unix-abstract-connect:///data/local/tmp/debug.sock",
                ]
            }
        ]
        // ...
    }
    ```