# excalidraw-desktop
Unofficial desktop client for Excalidraw on Windows &amp; MacOS. It is just an electron wrapper for the website, I made this because I don't want to use it in a tab.

![windows client](./resources/windows.png)

# Installation
Head over to the [releases page](https://github.com/pgkt04/excalidraw-desktop/releases/). Follow these steps:
1. Visit the [Releases](https://github.com/pgkt04/excalidraw-desktop/releases/) page.
2. Download the appropriate installer for your operating system:
3. Once downloaded, run the installer and follow the on-screen instructions to install the Excalidraw desktop client.

## Macos Users
If you get the error "Is Damaged and Can’t Be Opened. You Should Move It To The Bin".  
You can run the command:
```bash
xattr -c /Applications/Excalidraw.app
```
This is because I don't have a developer certificate and its not notarized.

# Development or Building
Before building the project, ensure you have the following prerequisites installed on your system:

Prerequisites
Node.js (version 14.x or higher)
npm (comes with Node.js)
To clone and set up the project, follow these steps:

Clone the repository:

```bash
git clone https://github.com/yourusername/excalidraw-desktop.git
cd excalidraw-desktop
```
Install the dependencies:

```bash
npm install
```

## Running
Once the dependencies are installed, you can start the application in development mode.

To run the app in development mode:

```bash
npm run start
```
This command will open the Excalidraw desktop client in a development window.

## Building
To create a production build and generate executable installers:

### Local Building
Run the following commands:

```bash
# Build for all platforms (Windows, macOS, Linux)
npm run dist

# Build only for Linux (creates both deb and AppImage)
npm run dist:linux

# Build only deb package
npm run dist:deb

# Build only AppImage
npm run dist:appimage
```

The generated installers will be found in the dist folder.

### Automated Building via GitHub Actions
This repository includes GitHub Actions workflows for automated package building:

1. **Release Workflow** (`build-and-release.yml`): 
   - Triggers automatically when you create a new tag (e.g., `v1.0.1`)
   - Builds deb, AppImage, and universal packages (Windows .exe/.msi, macOS .dmg)
   - Creates a GitHub release with all package files attached
   
2. **Manual Build Workflow** (`build-manual.yml`):
   - Can be triggered manually from the GitHub Actions tab
   - Allows you to build for specific platforms (Linux, Windows, macOS, or all)
   - Uploads build artifacts that can be downloaded

#### Package Types Generated:
- **Linux**: `.deb` package and `.AppImage` portable application
- **Windows**: Portable `.exe` and `.msi` installer
- **macOS**: `.dmg` disk image

To create a release with automated builds:
1. Create and push a new tag: `git tag v1.0.1 && git push origin v1.0.1`
2. The workflow will automatically build all packages and create a GitHub release

 

