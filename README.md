# kiibohd-animation-generator
Node.js script for generating animations for kiibohd configurator import

TODO: add more here...

This requires node and npm to run. In order to use, cd to the repo directory and run "``npm install``", and then you can run "``node kiianigen.js {generator name} {ktype standard dir}``". See documentation in kiianigen.js script for more details on usage. Note that at this time, the arguments are positional, and at least the generator name is required (unless you wish to see the generator names, as detailed below).

Generator names can be found in the "generators" object definition in the kiianigen.js file, or by invoking "``node kiianigen.js``" with no specified generator. This will print out all available generators.

NOTE: At this point I would not recommend running with "all" generators unless you comment out some of them. I've had issues flashing the keyboard with all the current animations, haven't had time to figure out why that is.

Workflow:
1. Run kiibohd configurator and output the configuration the way you like it (such as swapped keys for mac, etc. etc.)
2. Move that configurator generated directory next to the directory for kiibohd-animation-generator named "KType-Standard"
3. Run "``node kiianigen.js {generator name} {ktype standard dir if not at ../KTypeStandard}``"
4. Find the latest output in the json_out directory, copy contents
5. Open kiibohd configurator, click the up arrow/import button and paste the contents of the json file into the text box.
6. Click the down arrow/export button in the configurator
7. Set the keyboard in flash mode and click the Flash button in the configurator.
8. Once done,  you should be able to press f1:Q, f1:W, f1:E, etc. to toggle the animations.
