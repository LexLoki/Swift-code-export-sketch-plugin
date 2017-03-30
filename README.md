# Swift-code-export-sketch-plugin
A sketch plugin to generate code for programmatically implementation of the interface

Let's say you have somekind of view like UIView or UITableViewCell and you want to programmatically set their contents.
Using sketch is easy to prepare the interface, but when it comes to turn the visual into accurate numbers, things might get way tricky, especially for universal devices.
With this plugin you can select an Artboard Layer you used to represent the view, put all the contents there and then generate the code to create it programmatically. No storyboard, no bugs, no worries (or less at least).

## How to use:

1. Select an Artboard Layer
2. Go to Plugins>Swift_Code_Export> and select the desired export.
3. Click on the text of the box, press Cmd+a to select the whole code, copy and paste it where you need (viewDidLoad,layoutSubviews,etc)
4. Above the code, create variables 'w' and 'h' and assign to them, respectively, the width and the height of the view where you are placing the elements. They are used to calculate the right proportion and place the elements accordingly.
5. Switch the UIView ocurrances to whatever components you are using.

## Exports:
* Frame code: generates for each layer a, the line of code defining it's frame. `a.frame = CGRectMake(...)`
* Init+Frame code: generates for each layer a, the line of code initing the component with the frame. `a = UIView(frame: CGRectMake(...))`
* More to come...

## Example:
![alt tag](https://cloud.githubusercontent.com/assets/9408934/13299507/3d373344-db1a-11e5-8c32-2242c2186a6b.png)
![alt tag](https://cloud.githubusercontent.com/assets/9408934/13299513/416260f6-db1a-11e5-96ba-9b75ae01acee.png)
```
  var myImageView : UIImageView!
  var myLabel : UILabel!
    
  init(..){
      super.init(...)
      let w = contentView.frame.width;
      let h = contentView.frame.height;
      //Code from the plugin
      myImageView = UIImageView(frame: CGRectMake(0.067*w, 0.244*h, 0.25*w, 0.544*h))
      myLabel = UILabel(frame: CGRectMake(0.442*w, 0.344*h, 0.49*w, 0.344*h))
  }
```
## Installing Plugins (http://developer.sketchapp.com/introduction/)

If you double-click a .sketchplugin file, Sketch will copy it into the Plugins folder for you. Any commands that it implements should immediately show up in the Plugins menu.

Alternatively, you can install plugins by simply moving them into the Plugins folder yourself.

Note: Sketch also supports using aliases and links to individual Plugins, or to the Plugins folder itself. This allows you to place them elsewhere (for example, a Dropbox folder to keep multiple installs of Sketch synced).
