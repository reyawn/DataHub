DataHub
=======

INTRODUCTION
------------
DataHub provides [a]synchronous data sharing between objects without
requiring either to have direct access to or knowledge of the other.
Objects using DataHub to watch data need only know the property used
to share that data then implement a setter for that property i.e.:

All of DataHub's functionality can be added to any object by using its
enhance method as follows:

    DataHub.enhance (myObject); ).
    myObject.share ({ something: { data:This is fun!" }});


WATCHING
--------
    DataHub.watch    ({ something: myObject, something: myFunctionCallback }, { option: value });
+    OPTIONS:
+    newOnly: boolean    Ignores any "kept" data.
+    sync: boolean       Data will be shared to the watcher synchronously
+    queue: boolean      Multiple asynchronous shares will be queued instead of sharing only the latest value
+    name: string        Name of watcher
+    debug: boolean      Show debug output for activity relating to watcher

SHARING
-------
    DataHub.share    ({ something: dataToShare}, { option: value }, [optionalWatcherArray]);
+    OPTIONS:
+    keep: boolean       Data will be "kept" for late watchers
+    multiple: boolean   Data represents multiple arguments
+    sharer: string      Name of sharer
+    debug: boolean      Show debug output for activity relating to share

FREEING
-------
    DataHub.free    ({ something: 1 });

IGNORING
--------
    DataHub.ignore    ({ something: myObject });

CLEARING
--------
    DataHub.clearHub();

All DataHub actions can be chained i.e.:
    DataHub.share ({things:some}).watch ({things:this},{sync:true}).ignore ({things:this}).clearHub();

TODOS
-----
+   Go into further detail for queue + keep with late observers.