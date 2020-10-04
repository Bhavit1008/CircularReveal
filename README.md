# Easy Circular Reveal 😎
It is a very simple utility to use circular reveal in your project.
<br/>
## How to add.
Step 1. Add the JitPack repository to your build file <br/>
Add it in your root build.gradle at the end of repositories:
```
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
	}
}
```
Step 2. Add the dependency
```
dependencies {
	        implementation 'com.github.Bhavit1008:CircularReveal:0.0.1'
}
```

## How to use 🕶️
Step 1. Use it in that activity from which you want to go on another activity
```
EasyCircularReveal.presentActivity(EasyCircularReveal.Builder(
    this,
    viewClicked,
    Intent(this, YourOtherActivity::class.java),
    1500
))
```
Step 2. Use this in that activity where you want to reach from previous one.
```
private lateinit var mActivityCircularReveal: EasyCircularReveal

override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_other)

    val rootView: View = // ...
    mActivityCircularReveal = EasyCircularReveal(rootView)
    mActivityCircularReveal.onActivityCreate(intent)
}

override fun onBackPressed() {
    mActivityCircularReveal.unRevealActivity(this)
}
```
Step 3. Set color for reveal
```
builder.revealColor = ContextCompat.getColor(this, R.color.colorPrimary)
```
