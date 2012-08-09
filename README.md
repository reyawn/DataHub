DataHub
=======

Introduction
------------
DataHub provides [a]synchronous data sharing between objects without
requiring either to have direct access to or knowledge of the other.
Objects using DataHub to watch data need only know the property used
to share that data then implement a setter for that property i.e.:

All of DataHub's functionality can be added to any object by using its
enhance method as follows:

    DataHub.enhance (myObject); ).
    myObject.share ({ something: { data:This is fun!" }});


Using DataHub
-------------
### Watching

    DataHub.watch    ({ something: myObject, something: myFunctionCallback }, { option: value });

#### OPTIONS:
+    newOnly: boolean    Ignores any "kept" data.
+    sync: boolean       Data will be shared to the watcher synchronously
+    queue: boolean      Multiple asynchronous shares will be queued instead of sharing only the latest value
+    name: string        Name of watcher
+    debug: boolean      Show debug output for activity relating to watcher

### Sharing

    DataHub.share    ({ something: dataToShare}, { option: value }, [optionalWatcherArray]);

#### OPTIONS:
+    keep: boolean       Data will be "kept" for late watchers
+    multiple: boolean   Data represents multiple arguments
+    sharer: string      Name of sharer
+    debug: boolean      Show debug output for activity relating to share

### Freeing

    DataHub.free    ({ something: 1 });

### Ignoring

    DataHub.ignore    ({ something: myObject });

### Clearing

    DataHub.clearHub();

### Chaining
All DataHub actions can be chained i.e.:

    DataHub.share ({things:some}).watch ({things:this},{sync:true}).ignore ({things:this}).clearHub();

TODOS
-----
+   Go into further detail for queue + keep with late observers.
+   Perhaps switch default sync: false to async: false so watching is synchronous by default.

Copyright and License Information
---------------------------------
This source code was extracted from the WebOS Calendar application, available publicly at the location below:

https://github.com/openwebos/core-apps


All content, including all source code files and documentation files in this repository unless otherwise noted are:

 Copyright (c) 2010-2012 Hewlett-Packard Development Company, L.P.

All content, including all source code files and documentation files in this repository unless otherwise noted are:
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this content except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
