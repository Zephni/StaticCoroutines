# StaticCoroutines for C#

## Installing

1. Download StaticCoroutines.dll and add as a reference in your project
2. Add "using StaticCoroutines;" to the top of your C# file
3. Call Coroutines.Update(float deltaTime); every "Frame" and send it the time between frames


## How to use

After this you will probably want to use the CoroutineHelper.*Methods*. The public static methods are:


Action will run every update

```
Always(Action action);
```

Until boolean returns false action will run every update, when boolean returns true callback will be called

```
RunUntil(System.Func<bool> boolean, Action action, Action callback = null);
```

Waits until timer is reached since call, then calls the callback method

```
WaitRun(float Timer, Action callback = null);
```

Waits until boolean is true, and then calls the action method

```
RunWhen(System.Func<bool> boolean, Action action);
```

/// After timer amount of time, call the action method and repeat.

```
Every(float timer, Action action);
```

/// Until timer is reached since call run action, after timer is reached call callback

```
RunUntil(float Timer, Action action, Action callback = null);
```

Run for timer for X frames, passing current frame

```
RunOverX(float Timer, int Frames, Action<int> action, Action callback = null, int CurrentX = 0);
```

Will run action for timer amount of time, a percentage float from 0 to 1 will be passed into the action method. After time callback is called

```
RunFor(float timer, Action<float> action, Action callback = null);
```

Will run while booleanWhile is true, for timer amount of time, passing the percentage progress to the action method, and callback when finished

```
RunWhileFor(System.Func<bool> booleanWhile, float Timer, Action<float> action, Action callback = null);}
```

While booleanWhile is false run action until booleanUntil, then callback

```
RunWhileUntil(System.Func<bool> booleanWhile, System.Func<bool> booleanUntil, Action action, Action callback = null);
```


## Author

Zephni - [zephni.com](http://www.zephni.com)