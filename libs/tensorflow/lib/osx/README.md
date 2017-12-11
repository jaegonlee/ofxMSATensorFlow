Download the library from https://drive.google.com/file/d/1G1NyQkOueOYzRuK9OYSTqAa5Tl3VmZF0/view?usp=sharing

How to make shared libraries with Bazel at Tensorflow
https://stackoverflow.com/questions/38256180/how-to-make-shared-libraries-with-bazel-at-tensorflow
```
bazel build --config=cuda --config=opt --copt=-mavx --copt=-mavx2 --copt=-mfma --copt=-msse4.2 --action_env PATH --action_env LD_LIBRARY_PATH --action_env DYLD_LIBRARY_PATH //tensorflow:libtensorflow_cc.so
```

Build Tensorflow 1.4 Mac OS High Sierra 10.13 GPU Support 
https://gist.github.com/smitshilu/53cf9ff0fd6cdb64cca69a7e2827ed0f


If it doesn’t already exist, create a folder called ‘lib’ in your home folder. 

Copy libtensorflow_cc.so and libtensorflow_framework.so into ~/lib
(Make sure there’s a copy here too).

Error: Library not loaded: @rpath/libcudart.9.0.dylib
https://github.com/tensorflow/tensorflow/issues/6729

I don't know how to solve. So I just copied cuda libs to /usr/local/lib.

Alternatively see below for other ways of installing shared libraries
https://developer.apple.com/library/mac/documentation/DeveloperTools/Conceptual/DynamicLibraries/100-Articles/UsingDynamicLibraries.html#//apple_ref/doc/uid/TP40002182-SW10
