# vivid-alpha-testers
Build visually and code faster with Vivid — an in browser visual editor to modify your code

[Landing Page](https://vivid.lol)

## Install

Install Vivid with your preferred package manager.

```sh
# NPM
npm install -D vivid-studio

# Yarn
yarn add -D vivid-studio
```

## Usage
Vivid currently only supports apps with the following: React ≥ 17.0.2, NextJS ≥ 12.0.0, Tailwind. Vite, CRA support is coming soon. Paste the following into your top level file (any file that always gets imported should work).

```ts
if (process.env.NODE_ENV === "development") {
  import("vivid-studio").then((v) => v.run());
  import("vivid-studio/style");
}
```
Now, once you run your application in dev mode, you should have Vivid's full functionality! You'll first be prompted to give read/write permission in the directory which your application is located. 

## Inspecting elements

You can hold down <kbd>Option</kbd> while hovering over elements to replicate inspect functionality. Flex + grid support is coming very soon. 

## Selecting Components

You can click on any elements by <kbd>Option</kbd> clicking on any element. You can move between components and reach hidden components with the arrow keys: "inward" to a child component with <kbd>↑</kbd>, "outward" to a parent component with <kbd>↓</kbd>, and between adjacent sibling components with <kbd>←</kbd> and <kbd>→</kbd>.

## Executing Commands

Any time you select a component, the code pane will pop up. Any edits you make to the code pane will be reflected in your browser and in your code. If you want to edit styling even faster, you can pull up the command palette with <kbd>Command</kbd><kbd>K</kbd>. Typing a class in the command palette will add that Tailwind class to the selected component. If the class you are trying to add conflicts with an existing class, Vivid will replace the old class with your new input. If you type out a class that the component already has, Vivid will remove that class. 

## Known Issues
1. The app works with most Next applications. If it doesn't work with yours, shoot me a text with the error message - we'll fix it. 
2. The app does (infrequently) crash. If you just refresh your browser, it will almost always go away. All your changes get autosaved to your code, so you don't have to worry about losing your edits. 
3. Custom components show up a bit funky in the Vivid code pane. Also working on it. 
4. If you add a non-existent class from the command palette, Vivid won't check to make sure it's a valid Tailwind class before adding it. 
5. If you're editing in both Vivid and your IDE, you must save your changes in your IDE before going back to Vivid. Otherwise, the files created from your IDE and Vivid will diverge and you'll have to handle conflicts. 
