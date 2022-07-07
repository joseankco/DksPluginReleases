# Log Scrapper
The purpose of this task is to extract patterns of DarkBot log in order to get some stadistics, like occurrences of the pattern, occurrences per hour and more.

It will be usefull to extract data like GGs completed, rinusk collected, PET's deaths, whatever that Dark Orbit shows in its logs.

## Patterns
There is no need to match all the log line, a pattern can match a substring.

Patterns can be preceded with _(i)_ in order to make them case-insensitive, which means that it will interpret all strings as if they were lower-case.

There are two types of patterns that this plugin interprets: normal and numbered ones.

### Normal Pattern
Will match with exact strings in logs.
This kind of pattern will only count the occurrences and occurrences per hour.

```Palladium collected```
* Will match any log line that contains exactly _Palladium collected_.
* Matches: _Ore Palladium collected_, _Palladium collected_

```(i) palladium collected```
* Will match any log line that contains _palladium collected_ in any combination of upper and lower-case letters.
* Matches: _PALLADIUM collected_, _Palladium Collected_, _PaLLaDiUM CoLLEctEd_...

### Numbered Pattern
Will match with exact strings in logs that contains a number in the position we define.
This kind of pattern will count ocurrences, occurrences per hour, total and total per hour.
_Total_ stands for the sum of the number of the pattern in all occurrences.

```{n} uridium```
* Will match any log line that contains exactly _N uridium_.
* Matches: _failed to earn 10 uridium_, _10.000 uridium earned_, _5 uridium_
* In those matches, will sum 10 + 10.000 + 5 to the total

## Notes
While Live Logs Viewer can work on its own, Log Scrapper cannot. So, in order to use this task properly, Live Logs Viewer MUST be enabled in config and running.
Whenever you press Stop button in this task, you will also Stop Live Logs Viewer and vice versa.

The task uses RegEx to find the matches and it won't escape your input.
This means that, if you want to match a special RegEx character, you are going to need to escape it with backslash.

```
Pattern "P.E.T." matches "P.E.T.", but also matches "P1ExTl"
Pattern "P\.E\.T\." matches "P.E.T."
```