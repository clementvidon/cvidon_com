+++
title = "A Living Visual Archive"
seo_title = "A Living Visual Archive — Workflow and tools"
description = "A simple method to regain control of your images and keep them readable, portable, and usable over time."

date = 2026-06-10T12:00:00+02:00
category = "Guide"
tags = [
  "photography",
  "photo archive",
  "photo and video archive",
  "photographic archive",
  "visual archive",
  "personal visual archive",
  "personal media archive",
  "media archive",
  "photo workflow",
  "metadata",
  "digital files",
  "media management",
  "DAM",
  "cloud",
  "Bash"
]

draft = false
+++

Over time, our images accumulate without any real system.

We take photos with phones and cameras. We receive images through messages. We keep screenshots. We download, export, synchronize, and recover old folders from a computer or an external drive. The result is a collection that keeps growing, becomes increasingly scattered, and gradually slips out of our control.

The problem is not only the quantity. It is the heterogeneity. What we call our images is actually a fragile mass of files: photos, videos, RAW files, exports, screenshots, messaging attachments, edited versions, and duplicates.

On top of that come cryptic filenames, incomplete metadata, and sometimes corrupted files.

Photo libraries create a sense of order, and cloud synchronization provides a degree of safety. But a synchronized mass of files is not necessarily an archive under control.

The underlying problem is simple: knowing what you have, and being able to find it, sort it, move it, or reuse it just as easily today as in five or ten years.

The method presented here is based on a simple idea: before deciding where files should live, they first need a coherent foundation. That means making metadata as reliable as possible, especially creation dates, giving files stable names, and verifying that they are not damaged.

The goal is to create a healthy foundation that remains useful over time, regardless of the machine or application being used.

## Why not simply use a photo library?

Photo libraries are very useful for browsing, searching, selecting, editing, and sharing images. I use them too.

But they do not solve the same problem. In practice, images are often spread across several applications and storage spaces: a phone gallery, a cloud service, a catalog on a computer, local folders, or external drives. This is not necessarily a problem as long as each application stays within its own scope.

The problem appears when you want to bring all these files together to sort them, back them up, or archive them properly. Each application organizes, exports, and describes files in its own way. Once removed from these interfaces, the files become visible again for what they are: heterogeneous objects, named and described according to different conventions.

This is a question of dependency and interoperability.

A clear file foundation makes it possible to work with different tools without depending on the logic of any one of them. It avoids submitting the whole archive to the conventions or limits of a particular catalog. You can then choose the application best suited to each task while keeping an independent archive.

## What I mean by a living archive

I am not talking about cold storage where files are forgotten, but about a working structure: a system that keeps past and present images accessible and understandable.

A living archive should not only be able to grow. It should also be easy to refine.

Over time, some files lose their relevance, duplicates become visible, and categories become clearer. The goal is therefore not only to accumulate, but to make sorting, selecting, and reducing the archive as simple and safe as possible.

A good archive must remain simple to maintain. If it becomes too complex, it stops being used. It should be coherent, independent of any particular application, reliable, portable, and flexible enough to accommodate new sources.

In spirit, this follows classic data management principles: files should remain easy to find, accessible, interoperable, and reusable.

I wanted to bring these principles down to the scale of a personal archive, with a simple system:

- A system I can understand by opening a folder.
- A system that fits in my head rather than inside an application.
- A system that continues to make sense even if I change software, machine, or cloud service.

## Gather without mixing everything

Bringing files together does not mean dumping everything into a single folder.

From the start, I prefer to keep a few large, readable groups.

In my case, `Camera` receives files from my cameras. I usually organize them by year, then by shoot or session: series, project, event, trip, or commissioned work.

`Personal` gathers my personal visual archive in the broad sense: phone photos and videos, images received through messaging apps, screenshots, downloads, exports, and other personal visual files.

In my own archive, `Personal` contains several categories that reflect the way I keep files:

`Gallery` for everyday images and videos I choose for their quality or visual interest; `Memories` for personal memories; `Clippings` for visual fragments that document my time and my way of seeing it; `Inspo` for references and inspiration; and `Other` for what does not fit anywhere else yet.

```text
Archive/
├── Camera/
│   └── 2026/
│       ├── 0412-elvis-party/
│       └── 0514-palermo-weekend/
└── Personal/
    └── 2026/
        ├── Gallery/
        ├── Memories/
        ├── Clippings/
        ├── Inspo/
        └── Other/
```

These categories are neither universal nor fixed. Someone else might have `DIY`, `Outfits`, or `Cooking`.

This logic applies both to a first organization pass and to a regular routine: the goal is to bring files together without losing the contexts that make them understandable.

## The date as an anchor

For an archive to remain readable, files need to be sortable in an order that makes sense. The simplest order is often chronological: a date makes it possible to find a period, a session, an event, and above all to bring together files that are close in time.

But this information is not always obvious. A single file can contain several date-related fields, such as `DateTimeOriginal`, `CreateDate`, or `MediaCreateDate`, sometimes missing, modified, or contradictory.

The method therefore tries to determine the best possible date from the information available. This quickly becomes unrealistic to do by hand when processing many files, so it relies on a few simple automations: reading several date fields, choosing the best available one, then normalizing the relevant metadata.

The goal is not to produce an absolute truth in every case, but to create a stable and coherent foundation for organizing the archive.

Once this date has been established, it can become the anchor point of the filename.

## The filename as minimal infrastructure

I use a simple naming format:

```text
PREFIXYY_MMDD_HHMMSS_FILESIZE.EXT
```

For example:

```text
CV26_0320_025038_31188070.DNG
```

This means that heterogeneous files like:

```text
export_001.jpg
Screenshot_20260521-114207.png
photo_2024-12-31_20-42-19.jpg
DSC_8421.NEF
IMG_4822.MOV
R0004387.DNG
```

can become:

```text
CV26_0917_083102_01322839.JPG
CV26_0521_114207_00222780.PNG
CV24_1231_204219_00321333.JPG
CV24_1231_165930_29257528.NEF
CV23_0113_192213_00591823.MOV
CV18_0412_212530_30071244.DNG
```

Here, I use my initials, `CV`, as a prefix to indicate that these are my files.

The date and time in the filename make chronological sorting simple. Files created close together naturally end up next to each other. A series, a trip, a party, or a work session becomes readable again without depending on any application. Since the creation date is one of the most important pieces of information in a visual archive, writing it into the filename, not only into the metadata, reduces the risk of losing it through future exports, copies, or migrations.

The file size helps reduce collisions when several files share the same timestamp. It can also help identify certain duplicates, exports, compressions, modified versions, or lower-quality copies.

This is not elegant naming, but practical naming. Before any final folder structure is chosen, each file already carries its prefix, date, time, size, and format. This makes the files easier to sort, compare, move, back up, or reorganize.

## Final check

Before archiving or backing up, I simply check that the files can still be opened correctly.

This check helps avoid archiving files that were already damaged, or files that may have been damaged during normalization.

The files can then be moved to their storage destination: a cloud-synced folder, an external drive, a NAS, or another storage medium.

In my case, I simply move the archive to a cloud-synced folder. The service then takes over to verify, transfer, and synchronize the changes to my other copies.

## Keep it simple

The system deliberately relies on simple things: ordinary folders, readable filenames, small scripts, and standard tools. No specific application is required to understand and use the archive.

This is not about technical purity. It is about maintenance. The simpler a system is, the more likely it is to be used. The clearer it is, the easier it is to return to after several months. The more it relies on explicit conventions, the less it depends on my memory.

This is how the archive stays alive: because it is easy to change. New files can be added regularly, existing files can be reviewed, material that no longer matters can be removed, and the organization can be gradually refined.

## Who this is for

This system is intended for people who want to regain control of their personal visual archive using simple conventions that are readable and durable, without depending on any particular application.

It is especially useful for those who have accumulated files across multiple devices, cloud services, drives, and applications, and want a clean foundation that is easy to maintain and use over time.

## Get started

I turned this method into a practical guide with a few Bash scripts:

[photography-archiving-workflow](https://github.com/clementvidon/photography-archiving-workflow)

These scripts are simply the tools I use to apply this method. Other tools can serve the same purpose as long as the principles remain the same: establish a reliable date, name files clearly, verify that they can still be opened correctly, then place them into ordinary folders.

## Discussion

If you have questions, comments, or improvements, feel free to join the discussion:

- Article: [Substack](https://cl3don.substack.com/p/a-living-visual-archive)
- Workflow: [GitHub Discussions](https://github.com/clementvidon/photography-archiving-workflow/discussions)
