# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:



## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Shankar S B
Registeration Number : 212225230260
*/
```
## Activitymain.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageview"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:layout_marginTop="40dp"
        android:contentDescription="@string/app_name"
        android:src="@android:drawable/btn_star_big_on"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

    <Button
        android:id="@+id/blink"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="12dp"
        android:layout_marginEnd="4dp"
        android:text="Blink"
        android:shadowColor="@color/black"
        app:layout_constraintTop_toBottomOf="@id/imageview"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toStartOf="@id/rotate"
        app:layout_constraintHorizontal_weight="1" />

    <Button
        android:id="@+id/rotate"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="4dp"
        android:text="Clockwise"
        app:layout_constraintTop_toTopOf="@id/blink"
        app:layout_constraintStart_toEndOf="@id/blink"
        app:layout_constraintEnd_toStartOf="@id/fade"
        app:layout_constraintHorizontal_weight="1" />

    <Button
        android:id="@+id/fade"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="12dp"
        android:text="Fade"
        app:layout_constraintTop_toTopOf="@id/blink"
        app:layout_constraintStart_toEndOf="@id/rotate"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_weight="1" />

    <Button
        android:id="@+id/move"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="12dp"
        android:layout_marginEnd="4dp"
        android:layout_marginTop="20dp"
        android:text="Move"
        app:layout_constraintTop_toBottomOf="@id/blink"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toStartOf="@id/slide"
        app:layout_constraintHorizontal_weight="1" />

    <Button
        android:id="@+id/slide"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="4dp"
        android:text="Slide"
        app:layout_constraintTop_toTopOf="@id/move"
        app:layout_constraintStart_toEndOf="@id/move"
        app:layout_constraintEnd_toStartOf="@id/zoom"
        app:layout_constraintHorizontal_weight="1" />

    <Button
        android:id="@+id/zoom"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"
        android:layout_marginEnd="12dp"
        android:text="Zoom"
        app:layout_constraintTop_toTopOf="@id/move"
        app:layout_constraintStart_toEndOf="@id/slide"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_weight="1" />

    <Button
        android:id="@+id/stop"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="30dp"
        android:layout_marginEnd="30dp"
        android:layout_marginTop="25dp"
        android:text="Stop Animation"
        app:layout_constraintTop_toBottomOf="@id/move"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>

```

## MainActiviy.java
```

package com.example.animation;

import android.os.Bundle;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    ImageView imageView;
    Button blink, rotate, fade, move, slide, zoom, stop;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageview);

        blink = findViewById(R.id.blink);
        rotate = findViewById(R.id.rotate);
        fade = findViewById(R.id.fade);
        move = findViewById(R.id.move);
        slide = findViewById(R.id.slide);
        zoom = findViewById(R.id.zoom);
        stop = findViewById(R.id.stop);

        blink.setOnClickListener(v -> {
            Animation anim = AnimationUtils.loadAnimation(this, R.anim.blink);
            imageView.startAnimation(anim);
        });

        rotate.setOnClickListener(v -> {
            Animation anim = AnimationUtils.loadAnimation(this, R.anim.rotate);
            imageView.startAnimation(anim);
        });

        fade.setOnClickListener(v -> {
            Animation anim = AnimationUtils.loadAnimation(this, R.anim.fade);
            imageView.startAnimation(anim);
        });

        move.setOnClickListener(v -> {
            Animation anim = AnimationUtils.loadAnimation(this, R.anim.move);
            imageView.startAnimation(anim);
        });

        slide.setOnClickListener(v -> {
            Animation anim = AnimationUtils.loadAnimation(this, R.anim.slide);
            imageView.startAnimation(anim);
        });

        zoom.setOnClickListener(v -> {
            Animation anim = AnimationUtils.loadAnimation(this, R.anim.zoom);
            imageView.startAnimation(anim);
        });

        stop.setOnClickListener(v -> {
            imageView.clearAnimation();
        });
    }
}

```

## blink.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha
        android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:duration="500"
        android:repeatMode="reverse"
        android:repeatCount="infinite" />
</set>

```

## Move.xml
```
<?xml version="1.0" encoding="utf-8"?>
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0"
    android:toXDelta="200"
    android:fromYDelta="0"
    android:toYDelta="0"
    android:duration="1000"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />

```

## Fade.xml
```
<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="1500"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />

```

## Rotate.xml
```
<?xml version="1.0" encoding="utf-8"?>
<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="2000"
    android:repeatCount="infinite" />

```
## Slide.xml
```
<?xml version="1.0" encoding="utf-8"?>
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="-300"
    android:toXDelta="0"
    android:fromYDelta="0"
    android:toYDelta="0"
    android:duration="1500"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />

```

## Zoom.xml
```
<?xml version="1.0" encoding="utf-8"?>
<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="1.5"
    android:fromYScale="1.0"
    android:toYScale="1.5"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />

```

## OUTPUT
<img width="1920" height="1080" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/f3b5c07b-1b70-4c39-bb45-0e86d97af4bb" />
<img width="1920" height="1080" alt="Screenshot (61)" src="https://github.com/user-attachments/assets/20855383-4f33-4996-9170-0c127fff71a1" />
<img width="1920" height="1080" alt="Screenshot (62)" src="https://github.com/user-attachments/assets/a3a7f5d7-0871-4387-81c0-6ceceb2f38de" />
<img width="1920" height="1080" alt="Screenshot (63)" src="https://github.com/user-attachments/assets/8b23506a-6d3f-44ca-9b44-d4feb4931dce" />
<img width="1920" height="1080" alt="Screenshot (64)" src="https://github.com/user-attachments/assets/d2c68c5e-00f3-4741-ad3e-eb4d168f1c59" />
<img width="1920" height="1080" alt="Screenshot (65)" src="https://github.com/user-attachments/assets/a56587e6-5072-4966-861a-3cd8004e3da6" />




## RESULT
Thus Animation with Android Studio is implemented.
