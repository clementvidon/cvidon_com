+++
title = "A Living Photographic Archive"
seo_title = "A Living Photographic Archive — Photo archive, tools, and workflow"
description = "A simple method for organizing a living and durable photographic archive."

date = 2026-05-29T12:00:00+02:00
category = "Guide"
tags = [
  "photography",
  "photographic archive",
  "photo workflow",
  "metadata",
  "digital files",
  "DAM",
  "cloud",
  "Bash"
]

draft = false
+++

Photography does not only produce images. It also produces a fragile mass of files.

RAW files, JPGs, exports, videos, screenshots, files received or sent, compressed images, alternate versions, edited files, duplicated files, files whose names no longer mean anything, files with incomplete or inconsistent metadata.

Over time, finding an image no longer depends only on the image itself. It also depends on its name, date, format, metadata, folder, and the history of its copies, exports, compressions, and modifications.

An archive is therefore not only a place where files sleep. It is a system that makes it possible to find them, understand them, use them, and pass them on.

This problem does not only concern professional photographers. It concerns anyone who accumulates images over time: photographers, artists, designers, creators, or simply people whose phone and cloud accounts have slowly become large, messy, and difficult to handle.

Today, almost everyone becomes a kind of image collector. We photograph with our phones, receive images, send them, keep screenshots, edit and export from apps, sync everything to the cloud, and then gradually forget what this mass actually contains.

Cloud sync gives an impression of safety. It can protect against the immediate loss of a device or a drive. But it does not solve the deeper problem: knowing what one owns, being able to find it, understand it, sort it, move it, back it up elsewhere, and use it five or ten years later.

Just because an image is saved in the cloud does not mean we still truly control it.

The method is based on a simple idea: before deciding where every file should live, each file first needs to become reliable, readable, and sortable. That means establishing the most coherent creation date possible, checking that each file remains readable, and giving it a stable name that stays useful even outside a photo application.

Before:

```
Nikon Zf/DCIM/100ND750/DSC_8421.NEF

Ricoh GR III/DCIM/100RICOH/R0004387.DNG

iPhone 15/
├── DCIM/104APPLE/IMG_4821.HEIC
└── Downloads/export_001.jpg

Samsung Galaxy S23/
├── DCIM/Camera/20260526_194218.jpg
├── WhatsApp/Media/WhatsApp Images/IMG-20050518-WA0004.jpg
├── Telegram/Telegram Images/photo_2024-05-26_19-42-19.jpg
├── Pictures/Screenshots/Screenshot_20260521-114207.png
└── Download/
    ├── sticker_20260517_083102.webp
    └── 7f6c91e2a4f4d1d9.gif
```

Normalized baseline:

```
Archive/
├── Camera/
│   ├── CAMERA_CV26_0412_212430_30071244.DNG
│   └── CAMERA_CV26_0514_165930_29257528.NEF
└── Phone/
    ├── PHONE_CV05_0518_214409_01288211.JPG
    ├── PHONE_CV24_0526_194219_00322817.JPG
    ├── PHONE_CV25_0113_192213_00591822.HEIC
    ├── PHONE_CV26_0517_083102_00422819.WEBP
    ├── PHONE_CV26_0520_163201_00482731.JPG
    ├── PHONE_CV26_0521_114207_00118291.PNG
    └── PHONE_CV26_0526_194220_00112763.GIF
```

Possible organization:

```
Archive/
├── Camera/
│   └── 2026/
│       ├── 0412-elvis-party/
│       └── 0514-palermo-weekend/
└── Phone/
    ├── 2005/
    ├── 2024/
    ├── 2025/
    └── 2026/
```

## The Catalog Is Not the Archive

Photo apps and DAMs are very useful for viewing, organizing, selecting, searching, and editing images. They can recognize faces, group places, compile memories, filter series, or roughly find certain images. For many everyday uses, they are enough.

But they show their limits when it comes to organizing images that come from heterogeneous sources: several cameras, several phones, editing software, exports, messaging apps, screenshots, downloads, recovered files, or files transferred several times.

Each tool organizes images according to its own logic. As long as everything stays inside the same application, this abstraction works: we manipulate a catalog, not the archive directly. But behind the interface, there are still files, names, formats, dates, folders, versions, and metadata.

As soon as we want to migrate, archive, compare, extract, back up ourselves, or work across several storage media, the real system reappears: poorly named files, ambiguous dates, multiple exports, compressed versions, missing, modified, or contradictory metadata.

At that point, organization can no longer depend only on what an application believes it knows.

## What I Mean by a Photographic Archive

Both the content and the system must be designed to last.

I do not think of a photographic archive as cold storage where old images disappear over time. I mean it more as a working structure: a system that keeps past and present images accessible, understandable, easy to find, and easy to use.

A good archive must be simple to maintain. If the system is too complex, it will not be used for long. It must remain quickly accessible, both in part and as a whole. It must remain stable over time, independent from any specific application, understandable by a human, usable by machines, verifiable, and flexible enough to absorb new sources.

In spirit, this connects with some classic ideas in data management: making files findable, accessible, interoperable, and reusable. But I did not want to build a heavy system that would be difficult to maintain alone. I wanted a system that is simple, personal, readable, and robust in practice.

A system I can understand by opening a folder.

A system I can hold in my head, not one that only exists inside an application.

A system that continues to make sense even if I change software, machine, or cloud service.

## The Date as an Anchor

For an archive to remain readable, files need to be arranged in an order that makes sense. The simplest order is often chronological: a date makes it possible to find a period, a session, an event, or simply to bring together images that were made close to one another.

But this date is not always obvious. To locate the origin of an image, a file may contain several related fields, such as `DateTimeOriginal`, `CreateDate`, or `MediaCreateDate`. These pieces of information may be missing, modified, or contradictory.

My workflow therefore first tries to establish the best possible date from the available information. This step is not really viable by hand once many files are involved. The method relies on a few simple automations: reading several date fields, choosing the best available date, normalizing certain fields, and checking that the files remain readable.

The goal is not to produce a perfect truth in every case, but to create a stable and coherent basis for organizing the archive.

Once this date is found, it can become the anchor for the filename.

## The Filename as Minimal Infrastructure

I use a simple naming format:

```
PREFIXYY_MMDD_HHMMSS_FILESIZE.EXT
```

For example:

```
CAMERA_CV26_0320_025038_31188070.DNG
```

The prefix follows a simple convention:

```
SOURCE_OWNER
```

In my case, I use `CAMERA_CV` for files from my camera and `PHONE_CV` for files from my phone. `CAMERA` or `PHONE` indicates the source. `CV` indicates that these are my files.

Because the date and time are part of the filename, sorting files by name also sorts them chronologically. Images made close in time naturally end up next to each other. A series, a trip, a party, or a work session becomes readable again through a simple filename sort.

The creation date is one of the most important pieces of information in a media archive. Keeping it in the filename, not only in metadata, makes it less likely to be lost through exports, copies, or future migrations.

The file size helps reduce collisions when several files share the same timestamp. It also helps identify certain duplicates or less compressed versions quickly. Two very similar files with very different sizes often say something: an export, a compression, a modified version, a lower-quality copy.

The normalized extension makes the format immediately visible.

It is not an elegant name. It is an operational name. It turns the file into a more readable, more sortable, more portable object. In addition to making the work of possible third-party applications easier, it already makes a simple file explorer useful.

The idea is very simple: the filename becomes a small piece of infrastructure. Before choosing a final folder structure, each file already carries its source, date, time, size, and format. It becomes easier to sort, compare, move, back up, and reorganize later.

## Organizing by Source and Use

Once the files have been normalized, checked, and made sortable by name, the folder structure can remain simple. The system does not try to decide in advance where every file should live forever. It first creates a clean baseline, then leaves enough flexibility to organize according to actual needs.

My own organization is based on a simple distinction: source and use.

The source describes how a file enters the archive. In my case, `CAMERA_CV` refers to files coming from a controlled camera import. These are often images produced in an identified context: a shoot, a trip, a commission, a project. They can then be organized by session, with their RAW files, JPGs, sidecars, or exports.

`PHONE_CV` is deliberately broader. A phone is not only a device for taking pictures. It is also a place where images accumulate: personal photos, videos, screenshots, received files, downloads, references, app exports, compressed images, or images modified elsewhere.

Depending on the archive, all of this can be treated as one visual stream coming from the phone, or separated later in the folder structure. The right level of precision depends on what one wants to find again later.

The prefix therefore describes the origin or entry channel. The folder structure describes the use, context, or way in which the files should be found again.

For example, a simple organization can remain very broad:

```
Camera/2026/

Phone/2026/
```

In this case, `Phone/2026/` contains the phone’s visual stream for the year: photos, videos, screenshots, received files, downloads, or exports, depending on what one chooses to keep in the archive.

If the archive becomes too dense, the same logic can be refined without changing the principle:

```
Camera/2026/0412-elvis-party/
Camera/2026/0526-palermo-weekend/

Phone/2026/photos/
Phone/2026/videos/
Phone/2026/memories/
Phone/2026/screenshots/
Phone/2026/references/
```

The source remains the same; the use becomes more precise in the folder structure.

The system therefore does not try to impose a single definition of what counts as a photograph, a memory, a document, or a reference. It first creates a stable and readable baseline, then leaves enough flexibility to organize according to actual needs.

What matters is that each file keeps a clear identity, even if the folder structure evolves later.

## Staying Simple

I wanted this system to remain deliberately boring.

Ordinary folders. Readable filenames. Small scripts. Standard tools. No proprietary catalog as the only source of truth. No hidden database required to understand the archive.

This is not a rejection of photo applications. I also use software to view, select, edit, or publish images. But I do not want the meaning of my archive to depend only on them.

Tools change. Cloud services change. Catalogs can become difficult to export or read again. Clear folders, well-named files, and simple conventions remain easier to understand, copy, and maintain over time.

It is also a question of personal maintenance. The simpler a system is, the more likely it is to actually be used. The more readable it is, the easier it is to return to after several months. The more it relies on explicit conventions, the less it depends on my memory.

## Who This Is Useful For

This system is not a complete DAM. It is not a consumer app. It is not a magical solution for someone who never wants to think about organization.

It is for people who want to regain control over their media archive through simple, readable, and durable conventions.

That might be a professional photographer who wants to keep imports clean. A serious amateur who has accumulated years of photos. An artist or designer working with many images. A content creator mixing phone, camera, exports, and screenshots. Or simply someone who feels that their cloud contains too many files to still be truly manageable.

The goal is not to preserve files as dead objects.

The goal is to keep a photographic archive alive: readable by machines, understandable by humans, and useful enough to keep working with it years from now.

## Get started

I turned this method into a practical guide and a few Bash scripts:

[photography-archiving-workflow](https://github.com/clementvidon/photography-archiving-workflow)

The guide explains the workflow step by step. The scripts handle the parts that are not realistic to do manually at scale: cleaning and normalizing metadata, renaming files, and checking that media files remain readable.
