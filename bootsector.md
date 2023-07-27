# FAEP BLOG - BOOTSECTORS
Yes, as everyone knows, bootsectors are actually is the kernel on the startup of a C++ code. From now on, you can see the imagination of the `FAEP Bootsectors`.
## How It Works
The bootsector has 3 variables:
1. `bootsector` - Type: Boolean
    > This variable stores is the user in the bootsector either not.
2. `bootsector_loaded` - Type: Boolean
    > This variable stores do we have to load or not.
4. `bootsector_navigate` - Type: String
    > This variable stores where to navigate to read the bit.
3. `bootsector_loadid` - Type: Number
    > This variable stores the ID of the letter to start reading on.
***
#### `bootsector`
When we start the entire proccesor, we set it to `true`, so we know the user is in bootsector.
#### `bootsector_loaded`
When we load the app, we set it to `true`, then after loading, set it to `false`. This is useful for detecting is the app loading or not.
#### `bootsector_loadid`
This is used for debug like breakpoints. Set it to 5, it will start reading not from letter 0, it will start from 5.
## Redirects
We actually start reading the first bit 0, but actually using this code we acutally generate a `navigateTo` task `str`:
```
Set variable
[bootsector_navigate]
"Read " + [# bootsector_loadid]
```
We redirect and then we go to then next ID of the load.