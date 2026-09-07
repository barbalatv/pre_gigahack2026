# Протокол drill A–F

Один заполненный экземпляр на прогон. Сценарии — [preparation §3](../preparation.md), метрики и эвристики — [ai_workflow §8 и §3](../ai_workflow.md).

## Metadata

- Drill: A / B / C / D / E / F
- Date: ______
- Facilitator: ______
- Participants (с ролями): ______
- Starting commit SHA (если применимо): ______
- Planned timebox: ______ мин
- Actual duration: ______ мин

## Objective / scenario

- Что проверяем / наблюдаемый критерий: ______
- Исходные условия, входы и окружение: ______
- Вводимый failure (или «нет»): ______

## Timeline / observations

| Time | Event / action | Observation |
|---|---|---|
| ______ | ______ | ______ |
| ______ | ______ | ______ |
| ______ | ______ | ______ |

## Drill B/C metrics

Для B/C обязателен полный блок: значение + evidence; если измерить нельзя — причина. Для A/D/E/F заполнять только релевантное, остальные строки можно пропустить. N/A — с причиной, не вместо нуля.

Начало отсчёта / окно измерений: ______ · Фактически параллельных implementation tasks: ______.

| Metric | Measured value | Evidence / способ измерения |
|---|---|---|
| Time to first accepted demonstrable functionality (принята и интегрирована) | ______ мин | ______ |
| Time to first working deployment | ______ мин | ______ |
| Accepted merges per hour | ______ merge / ______ ч = ______/ч | ______ |
| Review / integration queue length | ______ задач; пик ______ | ______ |
| Ready-work idle time (готово → начало приёмки) | ______ мин по задачам; всего ______ | ______ |
| Agent outputs returned or rejected | возвращено ______; отклонено ______ | ______ |
| Integration rework count / объём доработки | ______ доработок; ______ мин; что переделано ______ | ______ |
| Recovery time after injected failure | ______ мин / N/A: ______ | отказ → восстановление: ______ |
| Spend / resource consumption (если измеримо) | разработка ______; продукт ______; единицы ______ | лимиты / квоты, billing, timeouts: ______ |
| Кто кроме Integrator самостоятельно запустил и объяснил систему | имя ______; что запустил / объяснил ______ | ______ |
| Фактическая жизнь веток (создание → принятый merge) | ______ мин по веткам | ______ |

## Main bottleneck

**Одно главное измеренное узкое место:** ______ · Измерение / ссылка на наблюдение: ______.

## Corrective actions

Не более трёх действий; ненужные строки удалить.

| Action | Owner | Due date | Evidence required | Retest status |
|---|---|---|---|---|
| ______ | ______ | ______ | ______ | не проведён / PASS / FAIL; дата, evidence: ______ |
| ______ | ______ | ______ | ______ | не проведён / PASS / FAIL; дата, evidence: ______ |
| ______ | ______ | ______ | ______ | не проведён / PASS / FAIL; дата, evidence: ______ |

## Calibration result

Это evidence для будущего решения; запись сама по себе не меняет эвристики в `ai_workflow.md`.

| Рабочая настройка | Результат / рекомендация | Измерение-основание |
|---|---|---|
| Recommended max parallel implementation tasks | ______ | ______ |
| Observed healthy branch lifetime | ______ мин | ______ |
| Threshold for stopping new builders / clearing integration queue | ______ задач / ______ мин ожидания | ______ |
| Other measured adjustment | ______ | ______ |
