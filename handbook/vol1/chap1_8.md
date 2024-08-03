# Creating Layers

Layers are a fundamental concept when modding Geometry Dash. In this tutorial, we'll cover how to create layers (`CCLayer`s) and understand their general layout. Let's dive in!

## Step 1: Creating the layer

To create a layer, we need to define a class. In this tutorial, we'll name our class `MyLayer` and provide an `init` function. Here's how you can do it:

```cpp
class MyLayer : CCLayer {
public:
  bool init() {
    return true;
  }
}
```

Now, it is very important to know that the `init` function has to be a bool function. Also, you may be asking: *Why does it say `public:` above the `init` function?* Here's why:

- Public means that the functions under them can be accessed by other files.
- Private means that the functions under them can only be accessed by other functions in the file itself.

## Step 2: Making them accessible

