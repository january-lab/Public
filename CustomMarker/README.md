<p align="center">
<img  width="300px" src="https://user-images.githubusercontent.com/26139791/64706378-9557db00-d4db-11e9-9b37-20ecbbcd27d2.jpg">
</p>

<br/>
<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![License: MIT](https://img.shields.io/badge/Release-1.0-blue)]()
<br/>

Custom Marker(CM) is an efficient shortcut to reveal the marker on the map. Fast and lightweight open source have bunch of functional customs to pool into a simple and easy to use interface.
CM supports changing dimensions, color and putting an image on it.

## Download
**Use Gradle:<br/>**
- Step 1: Add it in your root build.gradle at the end of repositories:

```gradle
allprojects{
  repositories{
    ...
    maven{
      url 'https://jitpack.io'
    }
  }
}
```

- Step 2: Add the dependency

```gradle
dependencies{
  implementation 'com.github.khanhuynh:custommarker:1.0'
}
```

**Or Maven:<br/>**
- Step 1: Add the JitPack repository to your build file

```xml
<repositories>
  <repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
  </repository>
</repositories>
```

- Step 2: Add the dependency

```xml
<dependency>
  <groupId>com.github.khanhuynh</groupId>
  <artifactId>custommarker</artifactId>
  <version>1.0</version>
</dependency>
```

## How do I use Custom Marker?
### Method 1: Insert Custom Marker to a layout
<br/>
<p align="center">
<img  width="300px" src="https://user-images.githubusercontent.com/26139791/64685171-bc4ce780-d4b0-11e9-9b6d-f15159766509.png">
 </p>
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/layout_content"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center_horizontal|center_vertical"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <com.khanhuynh.packages.CustomMarker
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:marker_color="#14B2ED"
        app:marker_padding="5dp"
        app:marker_radius="50dp"
        app:marker_size="100dp"
        app:marker_src="@drawable/default_avatar" />

</LinearLayout>
```

### Method 2: Add Custom Marker as a view to layouts programmatically
<br/>

```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        final CustomMarker customMarker = new CustomMarker(this);
        customMarker.setMarkerSize(R.dimen.default_marker_size_100dp);
        customMarker.setMarkerRadius(R.dimen.default_marker_radius_50dp);
        customMarker.setMarkerColor(R.color.default_marker_color);
        customMarker.setMarkerDrawable(R.drawable.default_avatar);
        customMarker.setMarkerPadding(R.dimen.default_marker_padding_5dp);

        final LinearLayout linearLayout = findViewById(R.id.layout_content);
        linearLayout.addView(customMarker);
    }
}
```

### Method 3: Add a loaded image from URL to Custom Marker
<br/>

```java
...
final ImageView loadedImage = new ImageView(this);
Picasso.get()
 .load("https://avatars1.githubusercontent.com/u/26139791?s=460&v=4")
 .into(loadedImage, new Callback() {
  @Override
  public void onSuccess() {
   customMarker.setMarkerBitmap(((BitmapDrawable) loadedImage.getDrawable()).getBitmap());
  }

  @Override
  public void onError(Exception e) {
   // Handle error here.
   // customMarker.setMarkerDrawable(R.drawable.default_error_place_holder);
  }
 });
...
```

### Method 4: Use with Tile Map API
<br/>
<p align="center">
<img  width="300px" src="https://user-images.githubusercontent.com/26139791/64690722-49953980-d4bb-11e9-884d-7ecd48a69218.png">
  <img  width="300px" src="https://user-images.githubusercontent.com/26139791/64690908-bdcfdd00-d4bb-11e9-8f00-799b3c011c5b.png">
  </p>

```java
...
tileView.addMarker(customMarker, 1000, 600, -0.5f, -1.0f);
...
```
### Method 5: Use with Google Map API
<br/>
<p align="center">
<img  width="300px" src="https://user-images.githubusercontent.com/26139791/64696044-b0205480-d4c7-11e9-8183-d34ede95d50c.png">
  <img  width="300px" src="https://user-images.githubusercontent.com/26139791/64696078-bf070700-d4c7-11e9-9e5c-da1fda3c38a3.png">
  </p>

```java
...
final CustomMarker customMarker = new CustomMarker(this);
customMarker.setMarkerSize(R.dimen.default_marker_size_100dp);
customMarker.setMarkerRadius(R.dimen.default_marker_radius_50dp);
customMarker.setMarkerColor(R.color.colorDefault);
customMarker.setMarkerDrawable(R.drawable.default_avatar);
customMarker.setMarkerPadding(R.dimen.default_marker_padding_5dp);

final BitmapDescriptor bitmapDescriptor = BitmapDescriptorFactory.fromBitmap(loadBitmapFromView(customMarker));
final MarkerOptions markerOptions = new MarkerOptions().position(imHere).icon(bitmapDescriptor);
mMap.addMarker(markerOptions);
...
```

## Status
Version 1.0 is now released and stable. Updates would be released periodically with new features and bug fixes.
## Compatibility
- Minimum Android SDK: CM v1.0 requires a minimum API level of 18.
- Recommended Android SDK: API level of 21 and above.
## Getting Help
To report any bugs or need helps just <a href="mailto:khanh28197@gmail.com">contact me</a>. 
## Thanks
- <a href="https://github.com/moagrius/TileView">Tile View</a> and <a href="https://www.google.com/maps">Google Map</a> provide Map API for testing terms.
- Thanks to <a href="https://square.github.io/picasso/#introduction">Picasso</a> for loading by disk caching.
- Everyone who reports bugs.
## Author
- Khanh Huynh - Analyst, Design Architect, Mobile Developer- Junior at Software Engineering, University of Science, HCM, Vietnam.
## License
MIT license.
