# ofxShivaVG

ofxShivaVG is a 2d-renderer for openFrameworks based on the ShivaVG OpenVG implementation. It provides improved rendering quality of 2d paths/curves, polylines and shapes, with optional line capping/joining.

Everything is rendered through openGL wich makes it much more performent than other cpu based 2d graphics libraries (Cairo, Quartz etc).



##Screenshots

Default oF renderer:

![Imgur](http://i.imgur.com/hMSeaZu.png)

ofxShivaVGRenderer:

![Imgur](http://i.imgur.com/hsh4HzM.png)



##Usage

First you MUST enable a stencil buffer in your ofProject. This is done by passing in "stencil" as part of the glut display string. Se example below:


```c
#include "testApp.h"
#include "ofAppGlutWindow.h"

//--------------------------------------------------------------
int main()
{
	ofAppGlutWindow window; // create a window
	
	// THIS IS THE IMPORTANT PART:
    window.setGlutDisplayString("rgba alpha double stencil samples>=4");
    
    
	// set width, height, mode (OF_WINDOW or OF_FULLSCREEN)
	ofSetupOpenGL(&window, 1024, 768, OF_WINDOW);
	ofRunApp(new testApp()); // start the app
}
```