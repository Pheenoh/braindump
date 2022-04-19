---
aliases: [electron]
---
# Electron
#computer-science 

Electron is a framework for building desktop applications using JavaScript, HTML, and CSS. By embedding Chromium and Node.js into its binary, Electron allows you to maintain one JavaScript codebase and create cross-platform apps that work on Windows, macOS, and Linux — no native development experience required.

Every electron app has exactly one main [[process]]. An electron app can, however, have many render processes.

## Main Process Modules
### App
Controls the lifecycle of an application using an event-based [[APIs|API]]

```typescript
// Run the createWindow function once the app is 'ready'
app.on('ready',createWindow);

// Run this inline function when all the windows are closed
app.on('windows-all-closed', () => {
	if (process.platform !== 'darwin') {
		app.quit();
	}
})
```

### BrowserWindow

Create and control browser windows.

```typescript
// In the main process.
const { BrowserWindow } = require('electron')

const win = new BrowserWindow({ width: 800, height: 600 })

// Load a remote URL
win.loadURL('https://github.com')

// Or load a local HTML file
win.loadFile('index.html')
```

### BrowserView

A BrowserView can be used to embed additional web content into a BrowserWindow.

```typescript
// In the main process.
const { app, BrowserView, BrowserWindow } = require('electron')

app.whenReady().then(() => {
  const win = new BrowserWindow({ width: 800, height: 600 })

  const view = new BrowserView()
  win.setBrowserView(view)
  view.setBounds({ x: 0, y: 0, width: 300, height: 300 })
  view.webContents.loadURL('https://electronjs.org')
})
```

### ipcMain

Communicate asynchronously from the main process to renderer processes.

```typescript
// In main process.  
const { ipcMain } = require('electron')  

ipcMain.on('asynchronous-message', (event, arg) => {  
	console.log(arg) // prints "ping"  
	event.reply('asynchronous-reply', 'pong')  
})  
  
ipcMain.on('synchronous-message', (event, arg) => {  
	console.log(arg) // prints "ping"  
	event.returnValue = 'pong'  
})
```

## Render Process Modules

### ipcRenderer

Communicate asynchronously from a renderer process to the main process.

```typescript

// Renderer process  
ipcRenderer.invoke('some-name', someArgument).then((result) => {  
// ...  
})  
  
// Main process  
ipcMain.handle('some-name', async (event, someArgument) => {  
	const result = await doSomeWork(someArgument)  
	return result  
})
```





