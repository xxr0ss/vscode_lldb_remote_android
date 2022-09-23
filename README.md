# Usage

* Install plugin `CodeLLDB` by Vadim Chugunov for VS Code.

* Install plugin `Tasks Shell Input` by Augusto, with this plugin we can use commandline for input in launch.json.

* (Optional) set `PYTHONPATH` in `.env` so that you can `import lldb` when writting python scripts.


* Specify how your lldb should connect to remote-android before attaching to target process in `.vscode/launch.json`:
    ```
    {
        "configurations": [
            {
                // ...
                "initCommands": [
                    "platform select remote-android",

                    "platform connect connect://<Device ID>:6666", // You can use `adb devices` to acquire device id
                    // "platform connect connect://localhost:6666", // you need to run `adb forward tcp:6666 tcp:6666`
                    // "platform connect unix-abstract-connect:///data/local/tmp/debug.sock",
                ]
            }
        ]
        // ...
    }
    ```

    * Start target on your Android device, and start debugging with VS Code. You can now attach to the `pid`, which is obtained via automatically run commandline.