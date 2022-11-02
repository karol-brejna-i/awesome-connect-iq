## Metadata structure design
Not all options/information will be presented to the end-user
we need to find a way to hold additional info somewhere.
This info can be both some input data (like who suggested the project, when it was added, what was the justification, etc.),
as well some additional data injected from external sources (like number of GitHub stars, forks, last commit, etc.).

The information can be used for housekeeping purposes (historical reference, improving the process),
but also to construct life UI, were you could filter, search, vote for items.


## Description design

Trying different options for presenting projects/material list:
- list with text (key: value, key: value)
- list with sub-items
- header and text
- table


List of _text entries with basic info only_ (collected when registering the project) could look like this:
- [matco/badminton](https://github.com/matco/badminton/) [Device App] - Badminton score tracker for Garmin watches. 🇮🇶🛒 <https://apps.garmin.com/pl-PL/apps/51606451-57e2-4f99-9420-2ba5a80b5df6>

List of _items with additional, externally obtained metadata_ like GitHub or IQ Store stats:
- [matco/badminton](https://github.com/matco/badminton/) [Device App] - Badminton score tracker for Garmin watches. **:octocat:** &#9282;8 &#9733;15 👁5 ⊙10 🗓2022.10.10 11:10. 🇮🇶🛒: <https://apps.garmin.com/pl-PL/apps/51606451-57e2-4f99-9420-2ba5a80b5df6>, Device App, 📅2022.10.03 ☆3.7/90 ⇩27926


List with sub-items would take more space, but there is a chance it is more readable (especially, when presenting additional info):
- [entry_name](entry_url)
  - Cateory: _category1, category2_
  - Description: _entry_description, entry_description_
  - :iraq:🛒: 🔗_URL_, _category_ 📅_lastUpdatedAt_ ☆_rating/votes_ ⇩100
  - GitHub: &#9282;100 &#9733;4 &#128065;3 	&#x1F4C5; 🗓2022.10.10 11:10
- [matco/badminton](https://github.com/matco/badminton/)
  - Category: Device App
  - Description: Badminton score tracker for Garmin watches.
  - 🇮🇶🛒: 🔗<https://apps.garmin.com/pl-PL/apps/51606451-57e2-4f99-9420-2ba5a80b5df6>
- [matco/badminton](https://github.com/matco/badminton/)
  - Category: Device App
  - Description: Badminton score tracker for Garmin watches.
  - **:octocat:** &#9282;8 &#9733;15 👁5 ⊙10 🗓2022.10.10 11:10
  - **🇮🇶🛒**: 🔗<https://apps.garmin.com/pl-PL/apps/51606451-57e2-4f99-9420-2ba5a80b5df6>, Device App, 📅2022.10.03 ☆3.7/90 ⇩27926

I am starting to think, that headers and text format and table format are not very useful for a this kind of makrdown document. On the other hand, they may be easier to parse (in case I would like to get the data from the list and inject new information/metadata). I won't investigate them here any further.

Maybe those kind of rich formatting is better suited for an web app that would present the information (plus additional data) and allow for searching, sorting, etc.