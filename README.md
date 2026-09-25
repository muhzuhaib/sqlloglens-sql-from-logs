# SqlLogLens - SQL from Hibernate, MyBatis and p6spy Logs

Support, documentation and legal documents for the **SqlLogLens** plugin for JetBrains IDEs.

**[Get it on the JetBrains Marketplace](https://plugins.jetbrains.com/plugin/34505-sqlloglens--restore-sql-from-logs)**

**This repository holds no source code.** It exists so that the plugin has a real issue tracker and
real documentation, both linked from the Marketplace listing.

- **Report a bug or ask for a feature:** [open an issue](../../issues). Every issue is read and
  answered.

---

## What the plugin does

Your application logs every statement with `?` placeholders and prints the real values somewhere
else. SqlLogLens puts the values back in, quoted correctly for their types, and gives you one
statement ready to paste into a database console.

## Free: restore from a selection

1. Select log lines in any editor or Run console.
2. Right-click, **Restore SQL from Selection**.
3. The statements are rebuilt, formatted and copied to the clipboard.

It reads Hibernate 5 and 6 bind logs (including formatted SQL spread over several lines), MyBatis
Preparing and Parameters blocks, and p6spy single-line logs, with or without the timestamp and
logger name your logging framework puts in front. Strings are quoted, numbers and booleans left
bare, nulls written as NULL, and a statement whose values do not add up is marked so you check it.

## Pro: capture while your application runs

- **Automatic capture.** Run or debug your application from the IDE and every statement it logs
  appears in the **SQL Log** tool window, values already in place. Nothing is added to your
  application.
- **History with a filter.** The last 500 statements, newest first. Type a table name to find the
  query you are after, double-click to copy it.

When nothing has been captured yet, the SQL Log window shows the logger settings each framework
needs:

| Framework | Setting |
| --- | --- |
| Hibernate 6 | `org.hibernate.SQL` at DEBUG and `org.hibernate.orm.jdbc.bind` at TRACE |
| Hibernate 5 | `org.hibernate.SQL` at DEBUG and `org.hibernate.type.descriptor.sql.BasicBinder` at TRACE |
| MyBatis | the logger of your mapper package at DEBUG |
| p6spy | route your datasource through p6spy with its default log format |

## Pricing

- **Restoring SQL from a selection is free**, with no time limit.
- **SqlLogLens Pro, personal:** $1.50 per month, or $15 per year.
- **SqlLogLens Pro, commercial:** $4.90 per month, or $49 per year.
- **30-day free trial** of Pro. Start it from the link in the SQL Log tool window, or from
  **Help, Manage Subscriptions**.

## Known limits

- Your application has to log its SQL and its bind values.
- Strings use standard SQL quoting. MySQL backslash escaping is not applied.
- A MyBatis value containing the text "), " and a p6spy line with "|" inside the SQL can be split
  in the wrong place, because those formats are ambiguous there.
- log4jdbc, jOOQ and Spring JdbcTemplate log formats are not read yet.
- Capture covers processes started from the IDE. Log files written elsewhere can be opened and
  restored from a selection.

## Privacy

SqlLogLens makes no network requests. Captured statements contain real values from your data, so
they stay in memory and are gone when the project closes.

## Support

Open an issue here. Include the IDE and version (**Help, About**), the plugin version, and a few
log lines that did not restore. **Replace any real customer data in them first.**

## Legal

- [End User Licence Agreement](EULA.md)
- [Privacy Policy](PRIVACY.md)
- [Third-party notices](THIRD-PARTY.md)

The plugin itself is not open source. This repository is for support and documentation only.
