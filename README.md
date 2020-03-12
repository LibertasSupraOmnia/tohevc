# tohevc
Converts h264 files to h265 using hevc_nvenc(nvidia hardware encoding) as well as hardware decoding.

Usage - Technical: 

tohevcbat [1] [2] (3)
tohevcdtsbat [1] [2] (3)

arg [1] : Encoding quality value. Either average bitrate(default) or crf. See Note [3] for how to use average bitrate and Note [4] for crf.

arg [2] : List of video files to encode. See Note [2] for how to make these lists.

arg (3) : Add /crf here to choose constant rate factor instead of default behavior(average bitrate). See Note [4] for how to use crf.

Usage - General:

Note [1]: Useful for compressing large video files into smaller h265 encoding. Also encodes all file types (.mp4, etc.) into .mkv to further save space.

Note [2]: Lists are generated by putting one file path after another in a text file with line-breaks, return characters, whatever you want to call them, after each individual path. If you don't want to do this manually you can use my list generating programs, extlist and rgxlist. Here are their github pages if you want them: (https://github.com/KaptainBflakes/extlist) (https://github.com/KaptainBflakes/rgxlist)

Note [3]: Average bitrates are in the format of bitrate. Inputting 1000 here is equal to 1 kilobit per second. This can be condensed by appending the first letter of different measurement factors to the end of the number. For example, 1K is 1 kilobit/s and 1M is 1 megabit per second, and so on. Use this for stable bitrate video.

Note [4]: Constant rate factor (crf) is a more general quality control, used for working with dynamic bitrates. It applies a different bitrate depending on this setting as well as the original bitrate. I'd tell you exactly how to use it, but frankly I don't really know myself. All I know is that it's a rate from 0 to 100 with 0 being totally lossless encoding that is usually way to large and 100 being incredibly lossy and only good for incredibly deep fried video memes. I've heard 12 or so is where it's at, quality wise, but I've not done extensive enough testing to confirm this for certain.

Note[5]: The "dts" in tohevctds refers to the use of "digital theater system", essentially surround sound audio in certain high quality video files. As dts requires entirely different ffmpeg settings, I've made it a separate program for simplicity sake. I might mesh these two programs together at some point, as well as reduce the name to just "tohevc" as these names were born out of modifications of that unreleased, single target program of the same function.

Note [6]: These executables are useful only if in a directory added to the system path and run from the command line. If you don't know how to add a directory to the system path, look it up, or copy it to a directory that has already been added. You could probably copy these to C:\Windows\system32 but I don't reccomend it.
