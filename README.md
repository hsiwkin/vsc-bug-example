# Example showing possible bug in VSCode causing difficulties in debugging VSC Extensions.

## Description
Console.logs from the inside of the iframe in the webview are not printed. Also it isn't possible to debug source file from the iframe.

## Step to reproduce
1. Start the server containing page we want to show in the iframe located in webview: `npm run start:server`
2. Press `F5` to compile and run the extension
3. Run the Hello World command from the Command Palette (Ctrl+Shift+P) in the new window
4. Open Webview Developer Tools console
5. Notice that instead of 2 console logs (from the webview and the iframe) two errors are printed, each of which saying: `VM93 main.js:10 [Violation] Avoid using document.write().`

## Expected behaviour
* Two console logs: `Hello from the iframe` and `Hello from the webview` are printed.
* It it possible to debug source files from iframe.
* It is possible to view DOM of ifrmame document in the Webview Developer Tools

## Actual behaviour
* Two errors are printed, each of which saying: `VM93 main.js:10 [Violation] Avoid using document.write().`
* It's NOT possible to debug source files from iframe.
* It's NOT possible to view DOM of ifrmame document in the Webview Developer Tools
