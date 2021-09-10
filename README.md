# basic-exoPlayer-YTExtractor
Learning Exo-Player basic with Nong intern

 Credit : [Android based YouTube url extractor](https://github.com/HaarigerHarald/android-youtubeExtractor) 

 ## Gradle

To always build from the latest commit with all updates. Add the JitPack repository:

    repositories {
        maven { url "https://jitpack.io" }
    }

And the dependency:

implementation 'com.github.HaarigerHarald:android-youtubeExtractor:master-SNAPSHOT'

## [](https://github.com/HaarigerHarald/android-youtubeExtractor#usage)Usage

It's build around an AsyncTask. Called from an Activity you can write:

    String youtubeLink = "http://youtube.com/watch?v=xxxx";
    
    new YouTubeExtractor(this) {
        @Override
        public void onExtractionComplete(SparseArray<YtFile> ytFiles, VideoMeta vMeta) {
            if (ytFiles != null) {
                int itag = 22;
    	    String downloadUrl = ytFiles.get(itag).getUrl();
            }
        }
    }.extract(youtubeLink);

The ytFiles SparseArray is a map of available media files for one YouTube video, accessible by their itag value. For further infos about itags and their associated formats refer to:  [Wikipedia - YouTube Quality and formats](http://en.wikipedia.org/wiki/YouTube#Quality_and_formats).


    

