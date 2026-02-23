# Speech Toolkit: LID + TTS Eval + Loudness Norm

Небольшой Google Colab ноутбук для 3 задач обработки речи:

1. Автоматическое определение языка речи (LID).
2. Сравнение качества нескольких TTS-систем.
3. Нормализация громкости речи.

Файл ноутбука: `speech_toolkit_lid_tts_loudness_colab.ipynb`

## Что умеет

- **Module A (LID):**
  - извлечение MFCC (с delta/delta2),
  - классификация языка (Whisper LID),
  - confidence и top-k вероятности,
  - метрики и графики при наличии `true_lang`.

- **Module B (TTS Eval):**
  - загрузка аудио по системам (`tts_system_A`, `tts_system_B`, ...),
  - расчет метрик (duration, RMS, спектральные, pitch, STOI опционально),
  - сравнительные графики и summary-таблица.

- **Module C (Loudness Norm):**
  - анализ уровней и динамического диапазона,
  - компрессия/гейт (опционально),
  - RMS/LUFS нормализация + ограничение пиков,
  - прослушивание before/after (включая примеры по языкам).

## Быстрый запуск в Colab

1. [Откройте](https://colab.research.google.com/drive/199P9a8IWF1Ff7IMTPt0HwjYlpva-r63f?usp=sharing) `speech_toolkit_lid_tts_loudness_colab.ipynb` в Google Colab.
2. Запустите ячейку установки зависимостей.
3. Перезапустите Runtime (если Colab попросит).
4. В ячейке `CONFIG` выберите режим данных:
   - `demo` (демо-примеры),
   - `upload` (ручная загрузка),
   - `drive` (папка в Google Drive).
5. Выполните ячейки по порядку.

## Входные данные

- Поддерживаемые форматы: `.wav`, `.mp3`, `.flac` (и другие при поддержке декодера).
- Для TTS-сравнения: отдельные папки систем с одинаковыми `utt_id` (обычно имя файла без расширения).
- Для LID-оценки (опционально): `metadata.csv` с колонками `filename,true_lang`.

## Выходные артефакты

Все результаты сохраняются в `results/`:

- CSV-таблицы по LID, TTS и нормализации,
- PNG-графики,
- итоговый отчет:
  - `speech_toolkit_report.md`
  - `speech_toolkit_report.html`

## Примечание

Для демо-датасета FLEURS в ноутбуке зафиксирована совместимая версия `datasets` (3.x), чтобы избежать ошибки `Dataset scripts are no longer supported`.

## Демо-аудио

### Language: de

Before:

🎧 Demo: [demo_01.wav](assets/demo_01.wav)

After:

🎧 Demo: [demo_02.wav](assets/demo_02.wav)

### Language: en

Before:

🎧 Demo: [demo_03.wav](assets/demo_03.wav)

After:

🎧 Demo: [demo_04.wav](assets/demo_04.wav)

### Language: ru

Before:

🎧 Demo: [demo_05.wav](assets/demo_05.wav)

After:

🎧 Demo: [demo_06.wav](assets/demo_06.wav)
