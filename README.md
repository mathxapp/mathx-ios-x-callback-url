## URL Scheme

MathX supports for integration with other apps via the through the [x-callback-url specification](http://x-callback-url.com/). You could find great [ready-to-install actions](actions.md).

MathX 2.2 is required for the following URL schemes.

## Open the application

`mathx://`

## Launching directly into a specific view

Use these URLs to directly access to a specific view rather than browsing.

#### General

	mathx://history

#### Calculator

	mathx://standardcalculator

#### Graphs

	mathx://graphicalrepresentation

#### Algebra

	mathx://determinantofamatrix
	mathx://inverseofamatrix
	mathx://matrixoperations
	mathx://linearequation
	mathx://quadraticequation
	mathx://cubicequation
	mathx://systemoflinearequations

#### Geometry

	mathx://distance
	mathx://dotproduct/pointfirstdefinition
	mathx://dotproduct/pointseconddefinition
	mathx://dotproduct/vectorfirstdefinition
	mathx://dotproduct/vectorseconddefinition
	mathx://vectorcalculator
	mathx://normofavector

#### Complex Numbers

	mathx://complexnumberscalculator
	mathx://complexnumbersconverter

#### Trigonometry

	mathx://specialangles
	mathx://converter
	mathx://pythagorastheorem
	mathx://generalizedpythagoreantheorem

## Actions

### /graphic

Show a graphic with the given function.

`mathx://x-callback-url/graphic?function=[text]&[action parameters]`

#### Parameters

- **function**: The function which will be represented graphically. You can specify the ouput (“y=” or “x=”). The default output is “y=”.
- **destination *(optional)*** : destination can be "cameraRoll","pasteboard","evernote" and "dropbox" to save the ploted graph.
- **zone *(optional)*** : this controls the cropping method used while exporting the graph. Possible values are full, top, bottom, left and right.
- **theme *(optional)*** : this controls the theme used while exporting the graph. Possible values are default, sepia and blackandwhite.
- **xaxisrange *(optional)*** : this controls the x-axis range used while exporting the graph. Possible values are extrasmall (-4 ; 4), small (-10 ; 10), medium (-20 ; 20), large (-40 ; 40) and extralarge (-100 ; 100).
- **yaxisrange *(optional)*** : this controls the y-axis range used while exporting the graph. Possible values are extrasmall (-4 ; 4), small (-10 ; 10), medium (-20 ; 20), large (-40 ; 40) and extralarge (-100 ; 100).
- **showlegend *(optional)*** : A boolean value (0 or 1) that determines whether the legend is shown.
- **x-success *(optional)*** : URL to open when the operation is complete.
- **x-cancel *(optional)*** : URL to open if the requested action is cancelled.
- **x-error *(optional)***: Error domain is "com.app-train.mathx.xcallback". Possible error codes are 1 (invalid function) and 2 (Photo library access)

#### Examples

Show the grahic of cos(x)

`mathx://x-callback-url/graphic?function=cos(x)`

Show the graphic of x=2

`mathx://x-callback-url/graphic?function=x%3D2`

Show the graphe of sin(x) and open an other app.

`mathx://x-callback-url/graphic?function=sin(x)&x-cancel=launchpro://`

### /calc

Compute the given function

`mathx://x-callback-url/calc?[action parameters]`

#### Parameters

- **function *(optional)***: The function which will be computed.
- **destination *(optional)***: destination can be “pasteboard” or “url”.
- **savecalculation *(optional)***: A boolean value (0 or 1) that determines whether the calculation is saved in your history.
- **x-success *(optional)***: URL to open when the operation is complete. It serves to pass the result back to the any other app. The answer is passed as the `[[ouput]]` variable if destination is set to “url”.
- **x-cancel *(optional)***:URL to open if the requested action is cancelled.
- **x-error *(optional)***: Error domain is “com.app-train.mathx.xcallback”. Possible error codes are 1 (invalid function) and 3 (invalid division).

#### Examples

Open the calculator

`mathx://x-callback-url/calc`

Compute 1+cos(30)

`mathx://x-callback-url/calc?function=1+cos(30)`