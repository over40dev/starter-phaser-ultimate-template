This version of the ultimate game parts template was built upon the phaser 3 project template by Richard Davey

https://github.com/photonstorm/phaser3-project-template

The following comments are taken from the documentation from the phaser3 project template

## Requirements

[Node.js](https://nodejs.org) is required to install dependencies and run scripts via `npm`.

## Available Commands

| Command         | Description                                                                     |
| --------------- | ------------------------------------------------------------------------------- |
| `npm install`   | Install project dependencies                                                    |
| `npm start`     | Build project and open web server running project                               |
| `npm run build` | Builds code bundle with production settings (minification, uglification, etc..) |

## Writing Code

After cloning the repo, run `npm install` from your project directory. Then, you can start the local development
server by running `npm start`.

After starting the development server with `npm start`, you can edit any files in the `src` folder
and webpack will automatically recompile and reload your server (available at `http://localhost:8080`
by default).

## Deploying Code

After you run the `npm run build` command, your code will be built into a single bundle located at
`dist/bundle.min.js` along with any other assets you project depended.

If you put the contents of the `dist` folder in a publicly-accessible location (say something like `http://mycoolserver.com`),
you should be able to open `http://mycoolserver.com/index.html` and play your game.
"# phaser-ultimate-template"

## Setting up a scene

Most of the common functions are found inside the baseScene class. You make scenes that extend this class to have access to those functions

```javascript
export class SceneMain extends BaseScene {
  constructor() {
    super("SceneMain");
  }
  preload() {}
  create() {
    //set up the base scene
    super.create();
  }
  update() {}
}
```

## Setting up an align grid - Wiliam Clarkson edits below

This project works by placing game objects on a grid that scales with a dynamically sized canvas.

You can do this inside any scene that extends baseScene

```javascript
create() {

        //set up the base scene
        super.create();

        //set the grid for the scene
        this.makeAlignGrid(11, 11);

        //show numbers for layout and debugging
        this.aGrid.showNumbers();


      }
```

## Adding Images

Use placeImage to add an image on the grid and scale it.

### Usage

this.placeImage(key,grid_number,percentage_of_screen_width)

### Example

this.placeImage("face",60,.25);

## Adding Text

You can place text on the grid by using placeText.

### Align-Grid-Usage

this.placeText(text,grid_number,text_style);

### Align-Grid-Example

this.placeText("Game Title",27,"TITLE_TEXT");

## Adding Reusable Text Styles

### Text-Styles-Usage

this.textStyles.regSimple(key, color, fontSize, font);

### Text-Styles-Example

this.textStyles.regSimple("SCORE", "#ffff00", TextStyles.SIZE_LARGE, "Impact");
