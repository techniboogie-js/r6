*The name "r6" is simply a numeronym of "require". In this case, 'r' followed by 6 letters.*

###### How to install
    npm install r6

###### How to use
    var r6 = require('r6')({ options });

###### Options
- **contextPath**: The root directory to search from. If not specified, r6 will use the directory of your main js file (entry point).
- **useGlobal**: Assigns the r6 function to the global scope as "r6" and returns *undefined*. This prevents you from having to re-require r6 in all js files.
- **legacy**: Utilizes local module search, and allows for the omitting of a leading forward-slash '/' for local modules. *This is to retain backwards-compatibility, but it's use is **not recommended***.

###### *Examples*
    // Instead of...
    var fu = require('../../../../fight/kung');


    // Loads module using the main js file's directory as the context
    var r6 = require('r6')();
    var fu = r6('/fight/kung');


    // Use with installed modules if you want
    // (In this case, the "optimize" option is suggested)
    var r6 = require('r6')({ contextPath: __dirname });
    var fu = r6('/fight/kung');
    var path = r6('path');


    // Use as a global
    // File #1
    require('r6')({ contextPath: __dirname, useGlobal: true });
    var fu = r6('/fight/kung');

    // File #2
    var booty = r6('/pirate/booty')

###### Change Log
**2.0.0**
- Removed optimize option and made leading slashes mandatory
- Added legacy option for backwards-compatibility
