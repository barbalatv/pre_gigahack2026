# AI onboarding: targeted revision и проверка

**09.09.2026.** Текущий результат — Qwen-first lifecycle. Запись предыдущего этапа 08.09 ниже сохранена как **история, superseded в части ChatGPT-first setup и review flow**; её продуктовые сведения и проверки не являются проверкой нового Qwen workflow. Участник начинает с [README](../README.md).

## Ревизия 09.09: начальный audit и границы

Перед изменениями: ветка `codex/ai-onboarding`, HEAD `942094a68bae8435590e82c46b440668ab0bf830`, реальный index чистый. В working tree были 6 изменённых tracked-файлов и 6 новых Markdown-файлов предыдущего этапа. Обычный diff --stat показывал только tracked: 31 вставка / 2 удаления; полный предыдущий пакет с untracked — 12 файлов, 727 вставок / 2 удаления. Состояние сохранено отдельно во временной папке для сравнения ревизии, без commit.

Информационная архитектура из трёх руководств принята и сохранена. Сохранены три примера на реальном учебном SHA, реальные имена scripts, различение code inspection и runtime, scope discipline, relevant inspection, WIP и существующие Gates A–E. AI orchestration, роли команды, стратегия challenges, Git workflow и календарь/drills не переписывались. Прежнее исправление номера §8 в technical_starter_kit сохранено без новых изменений этого файла.

## Изменение модели и файлов

Qwen Studio теперь default free Project Brain, Antigravity + Gemini — default Executor. Подготовка контекста, постановка, execution, evidence, независимое от исполнителя review и targeted fix-up образуют полный lifecycle. Qwen помогает до и после реализации, но не получает человеческие полномочия. В operating_decisions §7 добавлено только явно принятое пользователем уточнение 09.09 и датированная пометка сверху: источник внутренних решений согласован с руководствами.

| Artifact | Изменение относительно предыдущего этапа |
|---|---|
| [ai_onboarding](../ai_onboarding.md) | Qwen setup, один Source, public/private context, новый step-chat, возврат evidence, альтернативы и fallback; сохранены польза AI и развитие навыка |
| [prompting_playbook](../prompting_playbook.md) | Provider-neutral lifecycle и advisory review; сохранены все три примера, добавлена явная симуляция дефекта → fix-up → повторное review |
| [Antigravity guide](../antigravity_gemini_workflow.md) | Сохранён запуск/inspection, усилен пакет evidence, возврат в исходный Qwen chat и человеческий Git gate |
| [Prompt Architect instructions](../templates/prompt_architect_instructions.md) | Логическое переименование прежнего ChatGPT-шаблона и provider-neutral ядро; старый файл удалён, дубликата нет |
| [generate_gemini_prompt](../templates/generate_gemini_prompt.md) | Контекст через curated export / доступный app repo / local Recon, самодостаточный контракт с evidence |
| [agent_task](../templates/agent_task.md) | Расширен единый handoff, добавлен advisory review и targeted fix-up в том же стандарте |
| [curated export](../context/project_brain_context.md) | Единственный новый artifact сверх принятой архитектуры |
| [README](../README.md), [ai_workflow](../ai_workflow.md), [preparation](../preparation.md), [team_rehearsal](../team_rehearsal.md) | Обновлены маршрут и cross-links; основной командный процесс и упражнения сохранены |
| [operating_decisions](../operating_decisions.md), эта запись | Датированное принятое решение и фактическая история проверки |

Переименование логическое относительно предыдущей незакоммиченной работы: старый шаблон был untracked, поэтому Git не показывает rename из HEAD. Все Markdown-ссылки, включая историческую запись ниже, направлены на новый путь.

## Контекст: один из пяти Sources

Выбран один consolidated export: правила контракта, scope, evidence и authority нужны вместе; одна версия проще в сопровождении. Разделение на два файла сейчас расходовало бы лишний слот без достаточной пользы. Четыре места оставлены под official brief, provider requirements, rules/judging и schema/другой ключевой документ. Task diff и debugging передаются в чат, а не становятся постоянными Sources.

Экспорт существенно короче исходного operational corpus; содержит только hierarchy, принятые границы, статусы утверждений, роли/authority, AI cycle, contract/handoff/verification, Git/integration и UNKNOWN. Он имеет originating links, дату и честную базу: HEAD **плюс незакоммиченная ревизия**, не приписывает новые правила старому SHA. Обновляется после источников истины в private preparation repository; не объявлен новым canonical document. Полные research-архивы, персональные детали и confidential inputs не включались.

Рабочие свойства Qwen (desktop, 5 файлов, отсутствие private GitHub, дополнительный public source) приняты **как вводные пользователя**, без market research и без заявления о тесте аккаунта. Для Qwen описаны действия по смыслу без неподтверждённых названий UI-кнопок. Antigravity-инструкции сохраняют дату предыдущей продуктовой проверки 08.09.

Preparation repo остаётся private. Будущий application repo планируется public условно на official rules/provider confidentiality; URL UNKNOWN. Это источник опубликованного дерева/кода/committed baseline, не local status, uncommitted diff или unpushed commits. Private/недоступное приложение обслуживается через targeted local Recon/evidence. Публикация secrets, credentials, private partner data, confidential brief, запрещённых datasets и внутренних preparation docs ради Qwen явно исключена.

## Review gate, fallback и совместимость

Цикл: human intent → context → Recon при необходимости → task contract → Antigravity execution → evidence → **тот же Qwen step-chat** → review → targeted fix-up / ACCEPTABLE → human Git/integration. Каждый следующий substantial step начинает новый чат; локальный fix-up остаётся в текущем. Continuity — поддерживаемые Sources и короткий итог, не обещание автоматической памяти.

Review сопоставляет исходный objective/negative case/scope/запреты с видимыми изменениями и реальным выводом проверок; проверяет связь acceptance с verification, оставшийся риск и новые architectural obligations. Недостаток evidence даёт точный запрос материалов. Найденный дефект даёт severity, evidence, expected correction и сразу узкий fix-up, сохраняющий правильную работу. ACCEPTABLE ограничен доступным evidence и не является разрешением модели на commit или гарантией корректности.

Полный человеческий diff review остаётся даже при компактном пакете для AI. Self-report «47 тестов проходят» не принят за verification; чтение чужого вывода не названо самостоятельным запуском reviewer. Независимость от исполнителя не устраняет возможную общую ошибку контракта.

Local checkpoint, branch completion/PR, merge/integration и release различены. Review особенно полезен перед заявлением готовности шага/ветки, возможен до commit по локальному diff и по уже сделанному checkpoint. Не вводилось обязательное разрешение модели на каждый commit. Для точности использована таблица решений strategy §4: merge — Integrator или Technical Deputy; release/freeze — Integrator.

Antigravity-only — полноценный fallback при недоступности Qwen или неоправданных затратах переключения: intent → recon/planning → human review постановки → execution → human evidence review. Он сохраняет контракт, но не имеет независимого Project Brain. ChatGPT, Claude и другие совместимые сильные Prompt Architects — optional / approved alternatives; уже существующий платный workflow не требует миграции. Стандартизован интерфейс, не vendor. Жёсткого порога минут нет: усилие определяется риском и скрытым контекстом.

## Конфликты и намеренно не добавленное

Исправлены старый ChatGPT-default, требование читать private preparation по GitHub, чрезмерный список Sources, переключение в новый чат ради review и недостаточно определённый post-implementation цикл. Сохранён смысл исторического примера Antigravity → Codex → Claude в team_rehearsal: это OBSERVED PRACTICE, не новый default. Исторический аудит ниже явно помечен superseded.

Содержательная сверка выполнена с README, EXECUTIVE_BRIEF, strategy, ai_workflow, preparation, technical_starter_kit, operating_decisions, team_rehearsal и agent_task; дополнительно с Git workflow и canon. Нового конфликта с полномочиями, gates, FACT/DECISION/RECOMMENDATION и разделением AI-ролей не найдено. Это редакционный вывод, не автоматическое доказательство отсутствия всех противоречий.

Не добавлялись второй task/handoff/review standard, отдельный review template, пять обязательных AI-агентов, тарифный обзор, автоматизация GitHub, новая Git policy, новый drill, новая структура команды или challenge strategy. Export пересказывает необходимый минимум существующего agent_task с прямым происхождением, а не вводит альтернативную форму.

## Novice simulation — 12 переходов

Редакционная симуляция по готовым документам, **не тест живого участника или аккаунта**:

| Шаг | Где участник находит действие | Результат прохода |
|---|---|---|
| 1. Настроить Qwen Project | onboarding §3 | Отдельный desktop Project, краткий профиль и ссылка на инструкции |
| 2. Добавить curated context | onboarding §3 → context/project_brain_context | Один конкретный файл, дата/происхождение доступны |
| 3. Сохранить Source budget | Таблица пяти мест там же | 1 занят, 4 в резерве; не загружать пять случайных originals |
| 4. Открыть новый step-chat | onboarding §4 | Новый substantial step отделён, fix-up остаётся в нём |
| 5. Написать намерение | Копируемый блок §4 / generator | Обычный язык; неизвестное разрешается через Recon |
| 6. Получить task contract | generator → agent_task | Самодостаточный блок, scope/acceptance/verification/evidence |
| 7. Передать Antigravity | executor guide §1–3 | Рабочая копия, база и контракт; relevant inspection разрешён |
| 8. Получить evidence package | executor §4–5 / agent_task | Tracked diff и новые файлы, status, реальные выводы и непроверенное |
| 9. Вернуть evidence Qwen | executor §5 | В исходный чат с контрактом, а не только публичный baseline |
| 10. Понять verdict | playbook §2 / agent_task | ACCEPTABLE, FIX REQUIRED, BLOCKED: MISSING EVIDENCE различены |
| 11. Получить targeted fix-up | playbook §3, симуляция счётчиков | Конкретный дефект, узкая правка, повторные проверки и возврат |
| 12. Перейти к human Git gate | playbook §2 / executor §6 | Recommendation отделена от checkpoint, PR, merge и release |

При проходе уточнено: task evidence отправляется в чат без расходования постоянных Sources; новые untracked-файлы передаются отдельно; краткий пакет AI не отменяет полный Scope gate; уже сделанный checkpoint не требует отката ради pre-commit review. Переходов, требующих устного пояснения автора, в этом редакционном проходе не осталось. Реальное пробное чтение участником остаётся следующим способом проверить удобство.

## Фактические проверки ревизии

Проверены **45 Markdown-файлов и 522 ссылки**. Новых структурных проблем и проблем в 14 новых/изменённых относительно HEAD документах нет. Проверены локальные цели ссылок, таблицы, закрытие code fences и Unicode. Восемь прежних неразрешимых ссылок в исторических archive/evidence остались без изменений: шесть в архивном canon, две на отсутствующие screenshots; это не PASS всех старых ссылок. Внешние URL повторно массово не проверялись.

`git diff --check` — exit 0; проверка diff через отдельный временный index, включающий untracked-документы, — exit 0. `git diff --cached --quiet` — exit 0, реальный index чистый. Старый путь переименованного шаблона не встречается ни в одном Markdown-файле. Собственного documentation checker в repository не найдено; использован временный checker прошлого этапа с узким разрешением на датированное дополнение operating decisions.

Сверка с HEAD подтвердила неизменность strategy, EXECUTIVE_BRIEF, canon, Git workflow, shift_handoff и drill_protocol; operating_decisions отличается только пометкой даты и новым подразделом §7. Относительно сохранённого предыдущего этапа в ai_workflow, preparation и team_rehearsal изменился только входной абзац со ссылками; technical_starter_kit побайтно прежний. Все пять scripts и необходимые исходники учебных примеров присутствуют в сохранённом проверенном срезе прошлого этапа. Это проверка сохранённой базы, не свежего remote main.

Поиск и содержательный просмотр active AI-docs: 5 упоминаний ChatGPT — совместимые альтернативы или прежний общий список разрешённых инструментов; обязательного/default ChatGPT больше нет. Формальное разрешение Qwen на commit/merge не вводилось; APPROVED встречается только в значении допустимой альтернативы. Единственное «Можно коммитить?» — явно плохой пример. 29 относящихся к self-report/verification мест проверены по смыслу: отчёт без evidence не принят за verification. Исторический ChatGPT-first текст ниже помечен superseded, ссылки обновлены.

Curated export: **11 965 символов против 144 980** в десяти основных originating operational documents — **8,3%** объёма по символам. Это один Source с датой, статусами и границами; короткие chat handoffs поддерживаются отдельно. Ревизия затронула 13 текущих Markdown-файлов относительно сохранённого прошлого этапа, включая новый экспорт и переименованный шаблон; старый шаблон удалён. Итоговый diff от HEAD включает 14 файлов, в том числе сохранённое прежнее исправление technical_starter_kit.

Временные результаты: `C:\Users\user\AppData\Local\Temp\gigahack-qwen-revision-20260909\qa-results.json` и `consistency-sweep.json`; снимок до ревизии — подпапка `before`. Финальная команда: `python -X utf8 C:\Users\user\AppData\Local\Temp\gigahack-qwen-revision-20260909\check_docs.py`. Проверяющий скрипт не добавлен в repository и не меняет реальный Git index. Полный diff --stat сохранён в qa-results и приведён в итоговом отчёте задачи.

Runtime приложения, интерфейс Qwen и новая сессия Antigravity в этой ревизии не запускались. Учебный review/fix-up явно SIMULATED; прежние реальные исходники и scripts остаются привязаны к учебному SHA, а не названы текущим main. UNKNOWN: будущий application URL, окончательные official/provider ограничения и доступность конкретных функций аккаунта. После принятия изменений экспорт надо привязать к фактическому commit и заменить Project Source. Необходимость реального novice trial остаётся риском удобства, а не заявленной выполненной проверкой. Commit, push, PR и deploy не выполнялись.

---

## История: этап 08.09.2026 (superseded в отмеченных выше частях)

# AI onboarding: аудит, архитектура и проверка

**Дата: 08.09.2026.** Рабочая запись для сопровождающего документацию; участник начинает с [README](../README.md). Это аудит учебного слоя, не пересмотр стратегии и не отчёт о выполнении учебных coding-задач.

## Gate A — repository audit

Начальное состояние рабочей копии: чистая `docs/execution-pack-v1`, HEAD `8012afafca699dca708b2cc09b295c1e682130f4`. GitHub `main` уже содержал merge этой работы: `942094a68bae8435590e82c46b440668ab0bf830`. `git diff --stat HEAD..origin/main` не показал различий файлов. Создана отдельная ветка `codex/ai-onboarding` от актуального `origin/main`; новых commits не создавалось.

Проинвентаризированы корневые документы, templates, research, архивы и evidence. Основная сверка: README, Executive Brief, strategy, operating_decisions, ai_workflow, technical_starter_kit, preparation, team_rehearsal, git_contribution_workflow и шаблоны. Canon, open_questions, pitch/claims и история research использованы для границ FACT/DECISION, evidence и устаревших baseline. Чужие исторические приложения и datasets из evidence не исполнялись; повторное исследование правил GigaHack не проводилось.

| Область | Что уже было | Пробел / решение |
|---|---|---|
| Стратегия, роли и полномочия | Полностью определены operating decisions v2.1 и strategy | Не менять и не назначать человеку роль ради onboarding |
| Operational AI workflow | FRAME, RECON/PROBE, DECIDE, ствол, BUILD/VERIFY/INTEGRATE, роли и параллелизм | Нужен учебный вход в этот процесс, не второй процесс |
| Контракт и handoff | `templates/agent_task.md`, WIP note и Acceptance Gates | Переиспользовать; уточнить источники, рабочее состояние, verification и общие изменения |
| Git | Fork/upstream, fresh branch, clean diff, PR и отдельное решение merge | Объяснить связь с действиями агента и видимостью локального diff |
| Практика | Два задания и наблюдавшиеся ошибки, risk-triggered Recon/Fix/Review | Использовать реальные примеры, не переписывать curriculum |
| Настройка ChatGPT | Отдельного пути Project → sources → GitHub → instructions нет | Добавить в onboarding с проверкой чтения и fallback |
| Генерация prompt | Есть короткие role prompts, но нет context compiler workflow | Добавить reusable запрос, который сам читает repository |
| Antigravity/Gemini | Есть исторический пример распределения инструментов | Дать актуальный execution guide для принятого рабочего инструмента |

## Gate B — информационная архитектура

Три руководства и два копируемых шаблона; эта запись — отдельная история проверки, не дополнительный урок.

| Новый файл | На какой вопрос отвечает |
|---|---|
| [ai_onboarding.md](../ai_onboarding.md) | Зачем менять привычку и как настроить ChatGPT/context с нуля? |
| [prompting_playbook.md](../prompting_playbook.md) | Как из намерения получить проверяемое задание, соразмерное сложности? |
| [antigravity_gemini_workflow.md](../antigravity_gemini_workflow.md) | Как выполнить задание в repository и передать проверенный результат? |
| [ныне prompt_architect_instructions.md](../templates/prompt_architect_instructions.md) | Какие краткие постоянные инструкции скопировать? |
| [generate_gemini_prompt.md](../templates/generate_gemini_prompt.md) | Как попросить ChatGPT самому собрать контекст и заполнить существующий контракт? |

Изменяемые файлы: README (два маршрута чтения и шаблоны), ai_workflow (входные ссылки), preparation и team_rehearsal (ссылки без изменения упражнений), agent_task (точечное расширение). В technical_starter_kit исправлена только ссылка на номер раздела operating decisions про разрешённую инфраструктуру: §8 вместо §7.

Отдельные `chatgpt_setup.md`, `gemini_task_prompt.md`, `ai_handoff.md` не добавлены: настройка помещается в onboarding, контракт/handoff уже имеют владельца. Не создавались агентная платформа, Rules-файлы с новой policy, persona-каталог, обязательные пять агентов или автоматизация GitHub.

## Продуктовые источники и пределы проверки

Официальные страницы прочитаны 08.09.2026. Это проверка документации, **не тест аккаунтов участников**. Для страниц ChatGPT использованы также их официальные Markdown-представления; индексатор не принимал `text/markdown`, поэтому они прочитаны прямым HTTP-запросом.

| Источник | Что подтверждает / ограничивает |
|---|---|
| [ChatGPT Projects](https://learn.chatgpt.com/docs/projects?surface=web) | Общие chats, sources и инструкции; Project не даёт прямого доступа к локальной папке |
| [Personalize ChatGPT](https://learn.chatgpt.com/docs/personalize) | Персональные инструкции и память; не гарантия памяти всех деталей задачи |
| [Plugins](https://learn.chatgpt.com/docs/plugins?surface=web), [Web](https://learn.chatgpt.com/docs/web) | Подключение сервисов, GitHub, доступные tools; установка не заменяет авторизацию |
| [Models](https://learn.chatgpt.com/docs/models), [Pricing](https://learn.chatgpt.com/docs/pricing), [Luna API](https://developers.openai.com/api/docs/models/gpt-5.6-luna) | Название GPT-5.6 Luna подтверждено; доступ во всех бесплатных Chat-аккаунтах не установлен, API limits не переносим на Chat |
| [Antigravity Getting Started](https://antigravity.google/docs/getting-started/), [Projects](https://antigravity.google/docs/projects/) | New Project/Add Folder, Local/New Worktree; фактическую базу нужно проверить |
| [Models](https://antigravity.google/docs/models), [Plans](https://antigravity.google/docs/plans) | Gemini 3.8 Flash; модельный доступ и квоты — разные сведения; персональные лимиты не измерены |
| [Artifact Review](https://antigravity.google/docs/artifact-review/), [Agent Settings](https://antigravity.google/docs/agent-settings) | Planning/Fast, review policy и отдельные права запуска команд |
| [Rules](https://antigravity.google/docs/rules-workflows/), [Features](https://antigravity.google/docs/features) | Пути Rules и VCS review; не основание вводить новые правила repository |

Неоднозначности разрешены явно: бесплатный ChatGPT/Luna и большие квоты Gemini — вводная команды, не проверка тарифа каждого участника; живой GitHub доступ не гарантирует точный SHA/мгновенную индексацию; Sources-копия не является autosync. На недоступные функции предусмотрен путь через текстовые источники и локальный Recon. Инструменты из исторического примера `Antigravity → Codex → Claude Code` не объявлены обязательной схемой: их роли сохранены, текущий массовый Executor — Gemini.

Архивные multi-team baseline и старые поисковые выводы не повышены до действующих instructions. Состав, направления, deadlines, freeze, права интегратора и шесть drills остались прежними.

## Gate D — consistency review

| Проверка | Результат содержательной сверки |
|---|---|
| `operating_decisions.md` / `strategy.md` | Нет новой структуры команды, стратегии, challenge priorities или Git policy; право приёмки у человека |
| `ai_workflow.md` | Minimal context/relevant inspection сохранён; источники — данные; нет голосования моделей; масштабирование builders и evaluation оставлены в исходном документе |
| `technical_starter_kit.md` | Спецификация starter не названа реализованным приложением; новые examples относятся к учебному repository, не к закрытому challenge |
| `preparation.md` / `team_rehearsal.md` | Рекомендация увеличивать сложность по одной оси; drills A–F и задания №1–2 не изменены |
| `git_contribution_workflow.md` | Fresh base, explainable diff, review отдельно от merge, проверки после интеграции; история не переписывается ради красоты |
| Templates | Один agent_task/handoff, существующие WIP и gates сохранены; shift_handoff и drill_protocol переиспользуются ссылками |
| Примеры и evidence | Есть три сложности, конкретные входы, failure cases и реальные команды; ожидаемое исполнение не названо выполненным |

Существующая неточность cross-reference в starter kit (§7 вместо §8) исправлена. Других конфликтов новых требований с действующими operational rules при этой сверке не обнаружено. Это результат редакционного review, не автоматическое доказательство отсутствия всех возможных противоречий.

## Gate E — novice simulation

Редакционный проход по пути новичка, **не наблюдение реального участника**:

1. README ведёт через цель → onboarding → prompting → execution → advanced workflow.
2. Объяснены создание Project, общие instructions, Sources и проверка чтения GitHub; есть fallback без покупки подписки.
3. Разделены repository подготовки и приложения; объяснено получение SHA и передача незапушенного diff.
4. Намерение идёт в готовый запрос; ChatGPT читает файлы сам, при UNKNOWN выдаёт Recon.
5. Самодостаточный prompt переносится в правильный Antigravity Project/ветку; описаны установка, clone, runtime, запуск и выбор модели.
6. Человек видит tracked и untracked изменения, запускает positive/negative case и отличает blocker от PASS.
7. Возвращает единый handoff; интегратор проверяет итоговую объединённую версию.

По этому проходу уточнены действия в меню Project/Sources и первый clone/запуск приложения. Остаточный педагогический риск: материал ещё не прошёл пробное чтение реальным участником. Рекомендуется наблюдать один самостоятельный проход до drill B, записав место затруднения и время до принятого результата.

## Проверки файлов

Проверены 44 Markdown-файла и 480 ссылок в их тексте: локальные цели, согласованность столбцов таблиц, закрытие code fences, отсутствие символа замены Unicode. В 12 новых/изменённых документах проблем не найдено; новых проблем относительно исходного HEAD нет. Это проверка локальных ссылок и структуры, не HTTP-проверка всех старых внешних источников.

Обнаружены **8 прежних неразрешимых локальных ссылок**: шесть в `research/archive/canon_v2_before_operating_decisions_2026-09-05.md` после переноса документа в архив и две ссылки на отсутствующие screenshots в сохранённом `research/evidence/nicolaivicol_chat-own-docs-ft-rag-readme.md`. Они не входят в новый путь чтения и оставлены как есть; это ограничения исторического пакета, не PASS всего link inventory.

`git diff --check` завершился с кодом 0. Проверка через временный Git index включила также новые untracked-документы, сохранив реальный index нетронутым. Protected files (strategy, operating decisions, Executive Brief, canon, Git workflow, shift_handoff и drill_protocol) сравнены с HEAD: содержимое прежнее.

Для примеров прямым чтением GitHub проверены tree, README, `package.json`, `.github/workflows/ci.yml`, компоненты, helpers и тесты учебного repository на SHA `6e5bc45f478272e80153fa112132051e885ccaea`. Все пять использованных scripts существуют. Два новых пути в среднем примере явно обозначены как предлагаемые к созданию.

Точные локальные команды финальной структурной проверки:

~~~powershell
python -X utf8 'C:\Users\user\AppData\Local\Temp\gigahack-ai-onboarding-audit-20260908\check_docs.py'
git diff --check
git diff --cached --quiet
git status --short
~~~

Одноразовый checker и `qa-results.json` сохранены в указанной временной папке, в repository не добавлены. Checker вызывает `git read-tree HEAD`, `git add --intent-to-add`, `git diff --check` и `git diff --stat` с отдельным `GIT_INDEX_FILE`, затем удаляет временный index. Первый запуск без UTF-8 не смог вывести результат из-за кодировки консоли; повтор выполнен с `-X utf8`. В checker также исправлен принудительный override `core.autocrlf=false`, который давал ложные массовые изменения CRLF; итоговая проверка использует настройки repository, сами файлы ради неё не переформатировались.

Runtime-тесты учебного приложения не запускались; реальная сессия участника и визуальная проверка всех rendered Markdown-страниц не заявляются выполненными. Commit, push, PR и deploy в этой работе не выполнялись.
