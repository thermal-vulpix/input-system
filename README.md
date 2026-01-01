Part of the thermal-vulpix systems collection.

# Before you use
Read the [official Unity documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.17/manual/index.html) for the new Input System.

# How to install
Clone the repository, drag and drop `input-system.unitypackage` inside your Unity 6 Project, and extract it.

You will get the following files:
- `Input System Action Asset`
- `Input System C# Script` (generated from the `Input System Action Asset` file)
- `Input System Prefab`

# Recommended structure
Without the existence of `Input System Prefab`, we can not read inputs, so we must drag and drop it inside the scene.

Couple the GameObjects with the respective `Input System Prefab` they wish to read from by placing them in the same scene, which you can then load/unload at once.

# How to use
To read and use inputs in a script, do the following:
- Define a reference to the `Input System Action Asset`: `[SerializeField] private InputActionAsset input;`, and drag and drop inside the editor.
- Define the action you wish to read: `InputAction inputAction = input.FindAction("ACTION_NAME");`.
- Enable said action: `inputAction.Enable();`.
- You can now access inputs from the `inputAction` variable. The Unity Input System features many different bindings, and you will need to reference the [official documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.17/manual/index.html). Example: `Vector2 movement = inputAction.ReadValue<Vector2>()`.
