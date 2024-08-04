# Creating Layers

Creating layers is a valuable skill when modding Geometry Dash. In this tutorial, we'll cover how to create layers (`CCLayer`) and understand their general layout.

## Step 1: Creating the layer

To create a layer, we need to define a class. In this tutorial, we'll name our class `MyLayer` and provide an `init` function:

```cpp
class MyLayer : CCLayer {
public:
    bool init() {
      return true;
    }
}
```

Now, it is very important to know that the `init` function has to be a bool function. Also, you may be asking: *Why does it say `public:` above the `init` function?* Here's why:

- `public` means that the functions under them can be accessed by other files.
- `private` means that the functions under them can only be accessed by other functions in the file itself.

## Step 2: Making them accessible

To make the layer accessible from other layers, we need to add 2 functions: `create` and `scene`. Here's what they do:

- `create` will create an instance of the layer
- `scene` will handle the transition to the new scene

Let's add them:

```cpp
class MyLayer : CCLayer {
public:
  static CCScene* scene() {
        auto scene = CCScene::create();
        scene->addChild(MyLayer::create());
        return scene;
    }

    static MyLayer* create() {
        auto ret = new MyLayer();
        if (ret && ret->init()) {
            ret->autorelease();
            return ret;
        }
        delete ret;
        return nullptr;
    }
    bool init() {
        return true;
    }
}
```
