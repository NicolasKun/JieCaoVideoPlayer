<a href="https://github.com/lipangit/JieCaoVideoPlayer" target="_blank"><img src="https://raw.githubusercontent.com/lipangit/JieCaoVideoPlayer/develop/screenshots/logo2x.png" style="max-width:100%;"></a>
--
<p align="center">
<a href="http://developer.android.com/index.html"><img src="https://img.shields.io/badge/platform-android-green.svg"></a>
<a href="http://search.maven.org/#artifactdetails%7Cfm.jiecao%7Cjiecaovideoplayer%7C3.6.3%7Caar"><img src="https://img.shields.io/badge/Maven%20Central-3.6.3-green.svg"></a>
<a href="http://choosealicense.com/licenses/mit/"><img src="https://img.shields.io/badge/license-MIT-green.svg"></a>
<a href="https://android-arsenal.com/details/1/3269"><img src="https://img.shields.io/badge/Android%20Arsenal-jiecaovideoplayer-green.svg?style=true"></a>
</p>

* This project need translators, mother language is english, you can change everything edit readme, release note, formate variable and annotation.
* Now the research target is android.media.MediaPlayer setSurface by more surfaces the video is always continuous.

Android truly full-screen capabilities, the Android platform to become the most widely used video playback controls. Q Group:490442439


[中文文档](README-ZH.md)

### 备份

## Features
1. Launching new Fullscreen Activity when playing video in fullscreen mode
2. Completely custom ui
3. In `ListView`、`ViewPager` and `ListView`、`ViewPager` and `Fragment` and other nested fragments and views situation, it works well
4. Gestrues to modify progress and volume
5. Adaptive to the screen size, where at least the width or length of the video is adaptive while the other  is centered on the screen
6. It will not disturb or change the playing state when entering or exiting fullscreen
7. [Support hls,rtsp](https://developer.android.com/guide/appendix/media-formats.html)
8. With limited storage, less than 60 kb
9. Put head data

## Effect

**[jiecaovideoplayer-3.6.3-demo.apk](https://raw.githubusercontent.com/lipangit/jiecaovideoplayer/develop/downloads/jiecaovideoplayer-3.6.3-demo.apk)**

![Demo Screenshot][1]

## Usage
1.Import library
```gradle
compile 'fm.jiecao:jiecaovideoplayer:3.6.3'
```

Or download lib

* [jiecaovideoplayer-3.6.3.aar](https://raw.githubusercontent.com/lipangit/jiecaovideoplayer/develop/downloads/jiecaovideoplayer-3.6.3.aar)
* [jiecaovideoplayer-3.6.3-javadoc.jar](https://raw.githubusercontent.com/lipangit/jiecaovideoplayer/develop/downloads/jiecaovideoplayer-3.6.3-javadoc.jar)
* [jiecaovideoplayer-3.6.3-sources.jar](https://raw.githubusercontent.com/lipangit/jiecaovideoplayer/develop/downloads/jiecaovideoplayer-3.6.3-sources.jar)

2.Add JCVideoPlayer in your layout
```xml
<fm.jiecao.jcvideoplayer_lib.JCVideoPlayerStandard
    android:id="@+id/custom_videoplayer_standard"
    android:layout_width="match_parent"
    android:layout_height="200dp"/>
```

3.Set the video uri, video thumb url and video title
```java
JCVideoPlayerStandard jcVideoPlayerStandard = (JCVideoPlayerStandard) findViewById(R.id.custom_videoplayer_standard);
jcVideoPlayerStandard.setUp("http://2449.vod.myqcloud.com/2449_bfbbfa3cea8f11e5aac3db03cda99974.f20.mp4"
                , "嫂子想我没");
jcVideoPlayerStandard.thumbImageView.setThumbInCustomProject("http://p.qpic.cn/videoyun/0/2449_43b6f696980311e59ed467f22794e792_1/640");
```

4.Remember to invoke `JCVideoPlayer.releaseAllVideos();` in `onPause()` of `Fragment` or `Activity`

#### Other APIs

Invoke `JCFullScreenActivity.startActivity(...)` to enter fullscreen directly.
```java
JCFullScreenActivity.startActivity(this,
    "http://video.jiecao.fm/5/1/%E8%87%AA%E5%8F%96%E5%85%B6%E8%BE%B1.mp4",
    JCVideoPlayerStandard.class,
    "嫂子别摸我");
```

Control play button,if state is normal it will play, if state is playing it will pause
```java
jcVideoPlayerStandard.startButton.performClick();
```

ProGuard
```
Need nothing
```

##[Custom UI](./README_CUSTOM_UI.md)

##Contributors

[Nathen](https://github.com/lipangit) [Derlio](https://github.com/derlio) [zhangzzqq](https://github.com/zhangzzqq) [carmelo-ruota](https://github.com/carmelo-ruota) [wxxsw](https://github.com/wxxsw)

## License MIT

Copyright (c) 2015-2016 节操精选 http://jiecao.fm

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[1]: ./screenshots/j6.jpg

