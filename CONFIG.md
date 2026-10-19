# Agent Configuration — AI Business Opportunity Advisor

**Configuration documented:** 2026-10-19  
**Platform:** Anthropic Console — Managed Agents  
**Agent:** AI Business Opportunity Advisor  
**Agent version:** 2 (Latest at time of inspection)  
**Model:** `claude-haiku-5-5`  
**Effort:** Low  
**Primary language:** Hebrew

## 1. Purpose and scope

The agent interviews small-business owners in Hebrew, diagnoses inefficient workflows, identifies up to three opportunities for AI and automation, evaluates business impact and risks, and prepares a phased implementation plan. It recommends solutions but **does not implement them**.

## 2. Model and runtime configuration

| Setting | Configured value |
|---|---|
| Platform | Anthropic Console / Managed Agents |
| Agent name | AI Business Opportunity Advisor |
| Agent version | 2 |
| Model | `claude-haiku-5-5` |
| Effort level | Low |
| Environment | `ai-business-agent-env` |
| Hosting | Cloud |
| Environment scope | Organization |
| Networking | Limited |
| Package managers | Not allowed |
| MCP servers via environment | Not allowed |
| Allowed outbound hosts | None configured |
| Additional packages | None |
| Environment metadata | None |
| Skills | None |
| Multiagent configuration | None |
| Custom tools | None connected |
| Credential vaults in test session | None |
| Session resources in test | None |

**Networking distinction:** The managed `web_search` tool permission is separate from direct outbound network access within the cloud environment.

## 3. Built-in tools and permissions

| Tool | Function | Permission |
|---|---|---|
| `web_search` | Search the web | Always allow |
| `web_fetch` | Fetch URL content | Always ask |
| `bash` | Execute shell commands | Always ask |
| `read` | Read files | Always ask |
| `write` | Write files | Always ask |
| `edit` | Edit files | Always ask |
| `glob` | Find matching file paths | Always ask |
| `grep` | Search file contents | Always ask |

No custom ROI Calculator, MCP server, or persistent memory integration was connected during this test.

## 4. Full system prompt

The following is the complete system prompt supplied by the user from the agent configuration on 2026-10-19.

```text
אתה AI Business Opportunity Advisor — סוכן מקצועי לאבחון הזדמנויות להטמעת AI בעסקים קטנים.

מטרתך לאבחן תהליכים עסקיים, לזהות הזדמנויות לייעול באמצעות AI ואוטומציה, להעריך כדאיות כלכלית ולהפיק תוכנית יישום מדורגת. אינך מבצע הטמעות או שינויים במערכות העסק.

כללי שיחה:
- תקשר בעברית מקצועית, ברורה ונגישה.
- שאל עד שתי שאלות בכל פעם והמתן לתשובה.
- אל תציע פתרונות לפני שהבנת את העסק.
- אל תמציא נתונים, מחירים, יכולות של מוצרים או תוצאות.
- הבחֵן בין עובדות, הערכות ומידע שלא אומת.

תהליך אבחון:
1. שאל על תחום העסק, גודלו, תהליכי העבודה, הכלים הדיגיטליים, משימות חוזרות, אתגרים ותקציב.
2. זהה עד שלוש הזדמנויות להטמעת AI. בחן לכל אחת את התועלת, המורכבות והסיכונים.
3. לאחר האבחון, השתמש בכלי web_search לחיפוש אוטומטי של פתרונות מתאימים, עד שלוש שאילתות בסך הכול לאבחון. אל תכלול מידע עסקי רגיש בשאילתות.
4. אם חיפוש נכשל, נסה שוב עם שאילתה משופרת במסגרת המגבלה. אם אין מידע מאומת, הצג פתרונות עקרוניים עם הסתייגות ברורה.
5. בדוק התאמה לצורכי העסק והצג מקורות כאשר קיימים.

ROI:
- השתמש רק בנתונים שבעל העסק סיפק.
- בקש נתונים חסרים לפני חישוב.
- אל תניח אחוזי חיסכון או עלויות.
- כאשר כלי ROI Calculator מחובר וזמין, השתמש בו לחישוב.
- אם הכלי אינו זמין, ציין זאת ובצע חישוב שקוף רק אם כל הנתונים הדרושים קיימים.
- הצג הנחות, נוסחאות ותוצאות; אל תציג הערכה כהבטחה.

דוח ותוכנית יישום:
- הצג סיכום קצר בשיחה.
- הפק דוח Markdown מפורט הכולל פרופיל עסק, אתגרים, עד שלוש המלצות, מקורות, ROI כאשר ניתן לחשבו, תוכנית יישום מדורגת, מדדי הצלחה ומשימות המשך.
- אם אין אפשרות ליצור או לשמור קובץ, הצג את תוכן הדוח בפורמט Markdown בשיחה והסבר את המגבלה.
- אל תבצע פעולות יישום בפועל.

זיכרון:
- לכל עסק מזהה Business ID ייחודי.
- גישה למידע שמור תתאפשר רק לאחר אימות הרשאת המשתמש לאותו עסק; מזהה העסק לבדו אינו אימות.
- כאשר אחסון מתמשך מחובר וזמין, טען רק מידע מאושר של העסק הנוכחי.
- שמור רק סיכומים עסקיים, המלצות, החלטות, חישובי ROI ומשימות פתוחות. אל תשמור תמלילי שיחות מלאים או פרטי לקוחות.
- לפני כל שמירה או עדכון, הצג את השינויים ובקש אישור מפורש.
- אל תטען שביצעת שמירה אם לא התקבל אישור והאחסון לא אישר הצלחה.
- בתחילת שיחה חוזרת, לאחר טעינת הזיכרון, סקור התקדמות והצע עדכון תוכנית.
- אפשר לבעל העסק לבקש תיקון או מחיקת מידע.
- אם הזיכרון המתמשך אינו זמין, הסבר שהמידע אינו נשמר בין פגישות.

הרשאות ובטיחות:
- חיפוש אינטרנטי מותר באופן אוטומטי במסגרת המגבלה.
- כתיבה, עריכה ומחיקת קבצים דורשות אישור בהתאם למדיניות הכלים.
- אל תחשוף מידע של עסק אחד לעסק אחר.
- אם כלי נכשל, דווח על כך והמשך רק במה שניתן לבצע באופן אמין.

פתח שיחה חדשה בשאלה:
שלום! אני כאן כדי לעזור לך לזהות הזדמנויות לשיפור העסק באמצעות AI. במה העסק שלך עוסק?
```

## 5. Actual test execution

**Session:** `AI Business Agent - Test 2`  
**Date:** 2026-10-19  
**Environment:** `ai-business-agent-env`  
**Configured session budget:** USD $1.00 (may be exceeded by up to one turn according to the session UI)  
**Observed session cost:** USD $0.03 at the captured point in the session; not necessarily the final charge.  
**Test data:** Fictional small body–mind therapy clinic, approximately 25 active clients, 15 sessions per week, NIS 350 per treatment, 5 administrative hours per week, 4 cancellations per month, and up to NIS 200 monthly tools budget.

### Observed behavior

1. Agent responded in Hebrew and asked no more than two diagnostic questions at a time.
2. Agent asked about client volume, scheduling systems, administrative time, budget, and treatment price.
3. Agent attempted two `web_search` calls (Google Calendar booking/reminders and WhatsApp Business replies/reminders). Both returned errors; the agent disclosed the failure and did not claim to have verified sources or prices.
4. Agent identified three opportunities: appointment reminders, self-service booking, and structured follow-up tracking.
5. Agent produced a detailed Markdown assessment with prioritization, transparent calculations, assumptions, risks, and phased implementation steps.
6. The agent requested approval for a `write` tool call to create a report under `/mnt/session/outputs/`. The user inspected and approved the request.
7. A downloadable Markdown report was created and its preview was inspected. The user downloaded the report locally.

### Limitations observed

- Web search did not succeed in this session; no externally verified vendor pricing or product capabilities were obtained.
- The proposed custom ROI Calculator was **not implemented**. Calculations were generated in the model response and should be checked before real business use.
- ROI sensitivity scenarios were explicitly labeled hypothetical; they were not evidence-based forecasts.
- Persistent cross-session business memory and authentication were **not implemented**.
- The planned Make, Google Sheets, and web-dashboard architecture in `Architecture.md` was **not connected** to this running agent.
- Hebrew text displayed with imperfect right-to-left alignment in Anthropic Console. Proper RTL display is a planned web-interface requirement.
- This was one illustrative test, not comprehensive acceptance testing or production deployment.

## 6. Project files

- [`README.md`](README.md) — Project overview and current status.
- [`SPEC.md`](SPEC.md) — Functional design, tool and memory plans, safety and tests.
- [`Architecture.md`](Architecture.md) — Proposed triggers, information flows, storage, Make integration, and dashboard.
- `CONFIG.md` — Actual model configuration and test evidence (this file).

## 7. Implementation status

**Implemented and tested:** Managed agent definition, system prompt, model and effort selection, built-in tool permission policy, cloud environment, interactive test session, and approved Markdown report file creation.

**Planned, not implemented:** ROI Calculator custom tool, durable authorized memory store, Make workflows, Google Sheets datastore, secure API backend, and interactive business dashboard.
