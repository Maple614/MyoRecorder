setting

以下よりMyoのAndroid SDKをダウンロード
https://support.getmyo.com/hc/en-us/articles/360018409792-Myo-Connect-SDK-and-firmware-downloads

Myo SDK の中に入っているmyorepositoryをProject直下に置く

app -> build.gradle の中に以下を追記しSync Project with Gradle Fileを押す
build.gradle
...
dependencies {
    ...
    repositories{
        maven{
            // this must point to the myorepository distributed with the Myo SDK
            url '../myorepository'
        }
    }
    implementation('com.thalmic:myosdk:0.10.0@aar')
}

app -> src -> main -> res　に　menu(フォルダ) -> main.xml　を追加
main.xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    <item
        android:id="@+id/action_scan"
        android:showAsAction="ifRoom"
        android:title="scan"
        />
</menu>
