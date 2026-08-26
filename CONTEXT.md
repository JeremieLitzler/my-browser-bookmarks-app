# Browser Bookmarks App

A single place to store and browse bookmarks gathered from multiple browsers (Chrome, Edge, a mobile browser), reachable from any device without exporting/importing bookmarks between browsers by hand.

## Language

**Bookmark**:
A saved link consisting of a URL and a Title (the link text shown for it). Every Bookmark is either a Public Bookmark or a Private Bookmark.
_Avoid_: Link, entry

**Username**:
The public, human-readable name a User picks at signup, used to address their Public Page (e.g. `/u/jeremie`). Chosen specifically so a User's email never needs to appear in a URL.

**Public Page**:
A per-User page, addressed by that User's Username, listing their Public Bookmarks to any visitor without authentication. Reachable only by a User sharing their own link directly — the app exposes no directory or listing of Users or their Public Pages.
_Avoid_: Profile

**Public Bookmark**:
A Bookmark shown on its owning User's Public Page.
_Avoid_: Shared bookmark

**Private Bookmark**:
A Bookmark visible only to its owning User, once authenticated.
_Avoid_: Hidden bookmark

**User**:
An authenticated individual who owns a personal set of Bookmarks and Folders. Every Bookmark and Folder belongs to exactly one User.
_Avoid_: Account, owner

**Folder**:
A named container, owned by a User, used to organize that User's Bookmarks. A Folder can contain Subfolders, and can be created, renamed and moved directly in the app. When an Import brings in a folder with the same name/path as an existing Folder (regardless of which Source it came from), they are merged into one Folder rather than kept separate.
_Avoid_: Category, collection

**Import**:
The repeatable action of loading an HTML bookmark export (produced by a browser's built-in bookmark-export feature) into the app. An Import carries over the exported Folder/Subfolder structure from its Source, and is matched against the User's existing Bookmarks via Duplicate Detection.
_Avoid_: Sync, migration

**Source**:
The originating browser/device an Import comes from (e.g. a work PC, a personal laptop, a phone browser). A given Source is expected to be imported from repeatedly over time, not just once. Source is a real-world label the User keeps track of themselves — the app does not store which Source a Bookmark or Import came from.

**Duplicate Detection**:
The rule applied during Import to recognize that an incoming Bookmark already exists in the app, keyed on URL. A match whose details differ from the existing Bookmark becomes an Import Conflict.

**Import Conflict**:
A Duplicate Detection match where the incoming Bookmark's Title and/or Folder placement differ from the existing Bookmark's. Added to a review queue the User works through at their own pace (not blocking the rest of the Import), choosing per attribute to keep the existing value, take the incoming value, or, for the Title, type a different one entirely.
_Avoid_: Merge conflict
