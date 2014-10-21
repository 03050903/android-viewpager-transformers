android-viewpager-transformers
==============================

A collection of view pager transformers

#Getting Started

Simply import this project into your IDE and reference the Library as an Android Library Project from your project. After configuration, instantiate the transformer animation you wish to use and set it as the [page transformer](http://developer.android.com/reference/android/support/v4/view/ViewPager.html#setPageTransformer(boolean, android.support.v4.view.ViewPager.PageTransformer)).

```java

// Reference (or instantiate) a ViewPager instance and apply a transformer
pager = (ViewPager) findViewById(R.id.container);

pager.setAdapter(mAdapter);

pager.setPageTransformer(true, new RotateUpTransformer());

```

#Creating Custom Transforms

All ViewPagerTransform implementations extend [BaseTransformer](https://github.com/geftimov/android-viewpager-transformers/blob/master/library/src/main/java/com/eftimoff/viewpager/tranformators/BaseTransformer.java) providing useful hooks improving readability of animations and basic functionality important when switching between animations. [ABaseTransformer](https://github.com/ToxicBakery/ViewPagerTransforms/blob/master/ViewPagerTransformsLibrary/src/com/ToxicBakery/viewpager/transforms/ABaseTransformer.java) provides three lifecycle hooks and two flags for default handling of hiding offscreen fragments and mimicking the default paging functionality of the ViewPager.

* [preTransform(View view, float position)](https://github.com/geftimov/android-viewpager-transformers/blob/master/library/src/main/java/com/eftimoff/viewpager/tranformators/BaseTransformer.java#L42)
 * Default implementation resets the animation state of the fragment to defaults that will place it on the screen if its position permits.
* [onTransform(View view, float position)](https://github.com/geftimov/android-viewpager-transformers/blob/master/library/src/main/java/com/eftimoff/viewpager/tranformators/BaseTransformer.java#L14)
 * Animations should perform all or most of their work inside this callback.
* [postTransform(View view, float position)](https://github.com/geftimov/android-viewpager-transformers/blob/master/library/src/main/java/com/eftimoff/viewpager/tranformators/BaseTransformer.java#L75)
 * Default implementation does nothing. This provides a logical location for any additional work to be done that is not directly related to the animation.

#Special thanks for
[daimajia](https://github.com/daimajia)

[ToxicBakery](https://github.com/ToxicBakery)