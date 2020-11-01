# QuickScan
<p align="center">
<img src="https://github.com/neekonsu/QuickScan/blob/master/app/src/main/res/mipmap-hdpi/icon.png?raw=true" width="256" title="QuickScan Logo"/>
</p>

# QuickScan: A student identification app for employing exisitng student ID cards for authentication in school events

QuickScan provides a simple solution for identifying students for event checkins and attendance records using existing smartphones, registries, and ID cards.

## Problem Statement

When I was in middle school, I found the school dances quite frustrating. We would line up outside, eager to get into the gym and have a time, and the only barrier between us and that underpaid DJ was the sign-in that featured your run-of-the-mill clipboard checklist. Our school issued every student an ID card at the beginning of each year, and I remember recognizing the barcode as `CODE-47` --- a common encoding for short alphanumeric strings. I soon realized that the barcode on each card simply represented our student ID number, and that gave me the idea to use these ID cards for the school dance sign-in. The first system I tried implementing was one that used our library's laser barcode scanners, however I couldn't understand their sparse documentation one bit, so I opted to make my own scanner. Without any meaningful understanding of computer vision, trying to implement scanning libraries was very difficult for me, but I ultimately got the scanner to work, and from there I connected the app to a realtime database to log all the sign-ins. I also created an administrator hub to consolidate all the parallel scanning uploads to one stream of sign-ins and checkouts. I wrote my app in native android, since I was sick of using Microsoft's cross-platform solution called Xamarin. I used Firebase for my backend, and I wrote the dashboard in React-js.

## Basics 

QuickScan offers a simple two screen interface for managing events.

`The landing screen` of the app has the user authenticate their `scanning session` with a unique identifier for their event; each event has a separate bucket for scanning-logs so that users can manage multiple events with from within the same interface while maintaining the organization of their data in the cloud. The scanning logs, `event-identifiers`, and metadata for each user are available through the `web-client` dashboard, which lends users access to all logs and events captured through the QuickScan app.

`The scanning interface` is a non-interactive page that automatically recognizes, scans, and uploads checkin-instances to the event bucket whenever an id-card passes the camera's view.

# Instructions:

Please clone the git repository for QuickScan, open the android project within the folder using Android Studio, and run the app on your mobile device. Feel free to distribute the APK and source at your convenience.

![Gif Of App In Action](./run.gif)