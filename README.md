*The name "r6" is simply a numeronym of "require". In this case, 'r' followed by 6 letters.*

###### How to install
    npm install r6

###### How to use
    var r6 = require('r6')({ options });

###### Options
- **contextPath**: The root directory to search from. If not specified, r6 will use the directory of your main js file (entry point).
- **useGlobal**: Assigns the r6 function to the global scope as "r6" and returns *undefined*. This prevents you from having to re-require r6 in all js files.
- **optimize**: Bypasses local module search, but requires the local modules to have a leading forward-slash '/'. Good to use if you intend to use r6 as a replacement for require(). *This is optional, to retain backwards-compatibility, but it's use is **recommended***.

###### *Examples*
    // Instead of...
    var fu = require('../../../../fight/kung');


    // Loads module using the main js file's directory as the context
    var r6 = require('r6')();
    var fu = r6('fight/kung');


    // Use with installed modules if you want
    // (In this case, the "optimize" option is suggested)
    var r6 = require('r6')({ contextPath: __dirname, optimize: true });
    var fu = r6('/fight/kung');
    var path = r6('path');


    // Use as a global
    // File #1
    require('r6')({ contextPath: __dirname, useGlobal: true });
    var fu = r6('fight/kung');

    // File #2
    var booty = r6('pirate/booty')
