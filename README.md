## Dixa not compatible with Koin > 4.0.0
Dixa crashing after calling `DixaMessenger.openMessenger(this)` with : 

```
Process: com.test.dixatest, PID: 13720
java.lang.NoClassDefFoundError: Failed resolution of: Lorg/koin/androidx/viewmodel/GetViewModelKt;
at com.dixa.messenger.ofs.l4$e.invoke(SourceFile:1)
at kotlin.UnsafeLazyImpl.getValue(Lazy.kt:81)
at com.dixa.messenger.ofs.l4.c(Unknown Source:2)
at com.dixa.messenger.ofs.l4.onViewCreated(Unknown Source:8)
at androidx.fragment.app.Fragment.performViewCreated(Fragment.java:3152)
at androidx.fragment.app.FragmentStateManager.createView(FragmentStateManager.java:608)
at androidx.fragment.app.FragmentStateManager.moveToExpectedState(FragmentStateManager.java:286)
at androidx.fragment.app.FragmentManager.executeOpsTogether(FragmentManager.java:2214)
at androidx.fragment.app.FragmentManager.removeRedundantOperationsAndExecute(FragmentManager.java:2109)
at androidx.fragment.app.FragmentManager.execPendingActions(FragmentManager.java:2052)
at androidx.fragment.app.FragmentManager.dispatchStateChange(FragmentManager.java:3327)
at androidx.fragment.app.FragmentManager.dispatchActivityCreated(FragmentManager.java:3237)
at androidx.fragment.app.FragmentController.dispatchActivityCreated(FragmentController.java:263)
at androidx.fragment.app.FragmentActivity.onStart(FragmentActivity.java:350)
at androidx.appcompat.app.AppCompatActivity.onStart(AppCompatActivity.java:251)
at android.app.Instrumentation.callActivityOnStart(Instrumentation.java:1706)
at android.app.Activity.performStart(Activity.java:9122)
at android.app.ActivityThread.handleStartActivity(ActivityThread.java:4231)
at android.app.servertransaction.TransactionExecutor.performLifecycleSequence(TransactionExecutor.java:214)
at android.app.servertransaction.TransactionExecutor.cycleToPath(TransactionExecutor.java:194)
at android.app.servertransaction.TransactionExecutor.executeLifecycleItem(TransactionExecutor.java:166)
at android.app.servertransaction.TransactionExecutor.executeTransactionItems(TransactionExecutor.java:101)
at android.app.servertransaction.TransactionExecutor.execute(TransactionExecutor.java:80)
at android.app.ActivityThread$H.handleMessage(ActivityThread.java:2773)
at android.os.Handler.dispatchMessage(Handler.java:109)
at android.os.Looper.loopOnce(Looper.java:232)
at android.os.Looper.loop(Looper.java:317)
at android.app.ActivityThread.main(ActivityThread.java:8934)
at java.lang.reflect.Method.invoke(Native Method)
at com.android.internal.os.RuntimeInit$MethodAndArgsCaller.run(RuntimeInit.java:591)
at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:911)
Caused by: java.lang.ClassNotFoundException: Didn't find class "org.koin.androidx.viewmodel.GetViewModelKt" on path: DexPathList[[zip file "/data/app/~~PQif8Wdzg5XgOdKjK2iAJg==/com.test.dixatest-RcZi262kRm8TNdS2tFlnoQ==/base.apk"],nativeLibraryDirectories=[/data/app/~~PQif8Wdzg5XgOdKjK2iAJg==/com.test.dixatest-RcZi262kRm8TNdS2tFlnoQ==/lib/arm64, /system/lib64, /system_ext/lib64]]
at dalvik.system.BaseDexClassLoader.findClass(BaseDexClassLoader.java:259)
at java.lang.ClassLoader.loadClass(ClassLoader.java:637)
at java.lang.ClassLoader.loadClass(ClassLoader.java:573)
at com.dixa.messenger.ofs.l4$e.invoke(SourceFile:1) 
```

## How to reproduce
Uncomment
```kotlin
 /*   implementation(libs.koin.core)
    implementation(libs.koin.android)
    implementation(libs.koin.androidx.compose)
    implementation(libs.koin.compose)
    implementation(libs.koin.composeVM)*/
```

