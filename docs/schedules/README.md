# Academy timetable feeds

Publish the [academy directory](https://kemalenver.github.io/bjj-tracker-website/schedules/academies.json) and timetable feeds under `docs/schedules/` on the `main` branch of the [Mat Time website repository](https://github.com/kemalenver/bjj-tracker-website). The app repository carries the initial files as test fixtures.

## Add an academy

1. Add a timetable JSON file in the same directory. Use the [SJJA Dulwich Hill feed](https://kemalenver.github.io/bjj-tracker-website/schedules/sjja-dulwich-hill.json) as an example.
2. Add an entry to `academies.json` with a unique, stable `id`, its display `name`, and the feed filename as `schedulePath`. Use lowercase letters, digits and hyphens for the ID and filename stem. The timetable’s `academyID` must match the directory entry.
3. Commit both files together. After Pages publishes the change, open Mat Time or pull down in Academies or Schedule. The directory controls discovery. Existing followers can still manage a delisted academy, so keep its feed available if it should continue receiving updates.

## Update a timetable

- Keep `schemaVersion` at 1 and keep the academy’s `academyID` fixed.
- Increase `revision` for every change, including rollbacks.
- Use an IANA time zone such as `Australia/Sydney`, `America/New_York`, or `Asia/Tokyo`. All slots in the feed use this zone. Weekly times are minutes after local midnight, with Monday as weekday 0 and Sunday as weekday 6. For example, 18:20 is 1100. Start and end must be on the same academy day.
- Keep a class’s UUID when changing its name, time or weekday. Give new classes new UUIDs. Remove a row to end that weekly class.
- Use `adults`, `children`, `teens` or `unspecified` for `audience`.
- The feed contains public timetable data. The first revision was checked against the academy’s [adults timetable](https://sjjadulwichhill.com.au/timetable/adults-timetable/) and [kids timetable](https://sjjadulwichhill.com.au/timetable/kids-timetable/).

After Pages publishes the file, open Mat Time or pull down on the schedule to check the update.
