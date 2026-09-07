# GigaHack 2026 — рабочий пакет подготовки

**Срез на 8 сентября 2026. Событие 25–27 сентября, Tekwill, Chișinău. Стратегический baseline v2.1 заморожен 5 сентября; практические lessons learned обновляются отдельно.**

Начать с [HOW WE WIN GIGAHACK 2026](EXECUTIVE_BRIEF.md).

**Baseline: одна onsite-команда, ровно пять человек, один выбранный challenge, цель — первое место в нём.**

Пять мест: Integrator · Technical Deputy · Product/Domain · Data/Evaluation/Reliability · UX/Demo/Surge.

Цели подготовки: **Tier A** — Orange / Smart City / AgriFood; **Tier B** — Energy / Medpark. **NOT TARGETED** — Open Challenge и оба cybersecurity-направления.

Планировочное допущение: трек может быть заполнен полностью — до пяти других серьёзных команд.

Прежний baseline «10–15 человек → 2–3 команды» отменён; его текст и аудит следов — в [архиве](research/archive/multi_team_baseline_2026-09-05.md).

**[operating_decisions.md](operating_decisions.md) — источник принятых внутренних решений.** При расхождении с рекомендациями он имеет приоритет; новые официальные ограничения учитываются по описанному в нём порядку.

## Что читать и кому

| Документ | Для чего |
|---|---|
| [Executive Brief](EXECUTIVE_BRIEF.md) | Короткое общее решение: 15 ответов и десять главных советов |
| [Operating decisions](operating_decisions.md) | Что решено: состав, зоны ответственности, AI, prebuilt, границы |
| [Стратегия](strategy.md) | Пять мест, права решений, timeline, Friday Exit Gate, ранжирование узких мест |
| [Выбор challenge](challenge_selection.md) | Восемь критериев, отсекающие ворота, Tier A/B, досье владельцев задач |
| [AI workflow](ai_workflow.md) | Ствол демонстрации, лимит параллельных задач, контракты, проверка |
| [Практические задания](team_rehearsal.md) | Задания №1–2, реальные failure modes, новые gates приёмки и RECON → FIX → REVIEW |
| [Git contribution workflow](git_contribution_workflow.md) | Fork/upstream, fresh branch, clean diff, PR, восстановление загрязнённой ветки |
| [Стартовый комплект](technical_starter_kit.md) | MUST PREPARE / IF TEAM KNOWS IT / ON DEMAND / DO NOT PREBUILD и acceptance-тесты |
| [Подготовка и drills](preparation.md) | Календарь до 25 сентября, шесть коротких drills, атака на план |
| [Ментор и pitch](pitch_playbook.md) | Правила отказа, доказательства по типам задач, две длины защиты, Q&A, backup |
| [Ресурсы Молдовы](moldova_resources.md) | Проверенные public APIs, ограничения госинтеграций, данные и закон |
| [Исторические evidence](historical_evidence.md) | 26 победителей, пять случаев, конкуренция и пределы выводов |
| [Открытые вопросы](open_questions.md) | Место в треке, briefs, доступы, judging, сдача, логистика |
| [Canon](canon.md) | Фактическая база с датой и источниками |
| [Источники](sources.md) | Происхождение существенных утверждений и ограничения доступа |

## Практическая подготовка

Учебный репозиторий: [barbalatv/utm-curs-i-orar-2027](https://github.com/barbalatv/utm-curs-i-orar-2027).

Первые упражнения уже используются как дешёвая подготовка к drills B/C/E:

1. **Задание №1 — contribution path:** актуальный fork → локальный запуск → отдельная ветка → одно маленькое UI-изменение → inspect diff → commit → push → PR → screenshot.
2. **Задание №2 — lesson counters:** ограниченная функция внутри существующего кода с учётом чётности недели, `0`, responsive UI и обязательной человеческой проверкой AI-результата.

Главный новый вывод: **clean diff и свежий base — часть корректности, а не косметика Git.** Правильная функция поверх устаревшего fork может откатить чужую работу; рабочий локально AI-generated diff может содержать постороннюю поломку parser/config. Поэтому перед review теперь есть отдельные gates Fresh base → Scope → Behaviour → Ownership → Handoff. Подробности — [team_rehearsal.md](team_rehearsal.md).

## Рабочие шаблоны

[Challenge card](templates/challenge_card.md) · [Реестр утверждений](templates/claims_ledger.md) · [AI task](templates/agent_task.md) · [Mentor notes](templates/mentor_notes.md) · [Submission checklist](templates/submission_checklist.md).

## Порядок действий

1. До **10 сентября** — назвать пятерых, распределить пять мест с заместителями, отправить вопросы организаторам.
2. До основных drills — провести кандидатов через базовый contribution workflow и убедиться, что fresh fork / feature branch / clean diff / PR не являются новым навыком на самом событии.
3. **~13 сентября** — drill A: выбор challenge (45–60 мин).
4. До **17 сентября** — стартовый комплект уровня MUST PREPARE, доступы и квоты, досье по пяти карточкам Tier A/B.
5. **~16–17 сентября** — drills B (AI-реализация, 60–90 мин) и C (интеграция, 45–60 мин).
6. **18 сентября** — заморозка инструментария: новых стеков и сервисов больше не вводим.
7. **~19 сентября** — drills D (отказ, 30–45 мин) и E (Deputy, 30–60 мин). **~22 сентября** — drill F: защита и Q&A.
8. **24 сентября** — логистика и offline bundle. **25 сентября** — brief, порядок кандидатов, первые часы по плану [strategy §6](strategy.md).

Полных репетиций на 6, 8 или 48 часов в плане нет: шесть коротких drills покрывают важные режимы отказа. Учебные задания не добавляют «Drill G» — они убирают базовый Git/AI overhead до начала основных drills.

Наличие официального UNKNOWN не переоткрывает уже принятое внутреннее решение.

## Как читать уверенность

- **FACT** — подтверждённое содержание первичного источника или явно описанной проверки.
- **OBSERVED PRACTICE** — конкретный исторический или собственный наблюдаемый случай, не универсальное правило.
- **INFERENCE** — аналитическое объяснение, не доказанная причинность.
- **RECOMMENDATION** — наш рабочий выбор; численные timeboxes не официальные нормы.
- **DECISION** — внутреннее решение из operating_decisions.md; не утверждение об официальном разрешении.
- **UNKNOWN** — данных недостаточно или материал не получен.

Отсутствие найденного правила не означает разрешения. Внутренние решения не превращаются в утверждения об официальных правилах GigaHack.

## Состояние

Публичный стратегический срез завершён: актуальный rulebook, окончательные briefs, финальная форма сдачи и окончательный состав команды остаются неизвестными — на них даны условия решения. Практические упражнения команды уже идут в отдельном учебном репозитории; они дали первые измеримые lessons learned по fork hygiene, scope control и review AI-generated diff. Starter-код в этом репозитории по-прежнему не реализовывался и не публиковался.

История исправлений: [аудит canon](research/canon_audit.md), [сверка с operating decisions](research/operating_alignment.md), [архив прежнего baseline](research/archive/multi_team_baseline_2026-09-05.md), [проверка пакета](research/verification.md). Материалы research — техническая история проверки, а не обязательное чтение команды.
