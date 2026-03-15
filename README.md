<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Резюме Бородина Дарья А4</title>
    <style>
        /* Глобальные сбросы и базовые типографические настройки для формата А4 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #e6e9f0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Segoe UI', 'Roboto', 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.45;
            color: #1e2b3c;
            padding: 20px;
        }

        /* лист А4 */
        .resume {
            width: 210mm;
            min-height: 297mm;
            background: white;
            box-shadow: 0 12px 35px rgba(0,0,0,0.2);
            margin: 0 auto;
            padding: 12mm 14mm 12mm 14mm; /* поля внутри документа */
            border-radius: 2px;
            display: flex;
            flex-direction: column;
            page-break-after: avoid; /* для печати */
            position: relative;
        }

        /* для точной печати */
        @media print {
            body {
                background: white;
                padding: 0;
            }
            .resume {
                box-shadow: none;
                width: 100%;
                height: auto;
                padding: 0.75in 0.6in; /* стандартные поля при печати */
                margin: 0 auto;
            }
            .contact-item, .badge {
                break-inside: avoid;
            }
        }

        /* заголовок — ФИО и дата рождения */
        .fullname {
            font-size: 28px;
            font-weight: 700;
            letter-spacing: 0.5px;
            color: #0b2b40;
            border-bottom: 3px solid #3a6ea5;
            padding-bottom: 4px;
            margin-bottom: 12px;
            display: flex;
            justify-content: space-between;
            align-items: flex-end;
        }
        .fullname span {
            font-size: 16px;
            font-weight: 400;
            color: #3e5f77;
            margin-bottom: 5px;
        }

        /* блоки */
        .section {
            margin-bottom: 18px;
        }

        .section-title {
            font-size: 18px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.8px;
            color: #1d4e7c;
            border-bottom: 1px solid #b0c7dd;
            padding-bottom: 4px;
            margin-bottom: 10px;
        }

        /* сетка для компактного размещения */
        .two-col {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 8px;
        }

        .education-detail {
            font-weight: 500;
            margin-bottom: 6px;
            background: #f4f7fc;
            padding: 6px 10px;
            border-radius: 4px;
        }

        .univ-name {
            font-size: 18px;
            font-weight: 600;
            color: #003366;
        }
        .univ-meta {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin: 6px 0 4px;
            font-size: 15px;
        }

        .period-badge {
            background-color: #d9e7f5;
            padding: 3px 12px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 500;
            display: inline-block;
            margin: 4px 0 6px;
        }

        /* навыки тегами */
        .skills-cloud {
            display: flex;
            flex-wrap: wrap;
            gap: 8px 10px;
            margin: 8px 0 4px;
        }
        .skill-tag {
            background-color: #eef2f7;
            border-left: 4px solid #3a6ea5;
            padding: 5px 12px 5px 12px;
            font-size: 14px;
            border-radius: 0 14px 14px 0;
            font-weight: 500;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }
        .skill-tag-alt {
            background-color: #e2eaf3;
            border-left-color: #2b5797;
        }

        /* списки */
        .compact-list {
            list-style: none;
            margin-top: 6px;
        }
        .compact-list li {
            margin-bottom: 6px;
            padding-left: 18px;
            position: relative;
            font-size: 14.5px;
        }
        .compact-list li::before {
            content: "▹";
            position: absolute;
            left: 2px;
            color: #1d4e7c;
            font-weight: bold;
        }

        /* контактная информация строка */
        .contact-row {
            display: flex;
            flex-wrap: wrap;
            gap: 24px;
            background: #f0f5fb;
            padding: 12px 16px;
            border-radius: 12px;
            margin: 15px 0 10px;
            font-weight: 500;
            align-items: center;
        }
        .contact-item {
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .contact-item i { 
            font-style: normal;
            font-weight: 400;
            color: #3a6ea5; 
            font-size: 1.2rem;
        }

        /* прочее: личные качества, мелкие детали */
        .personal-box {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin: 8px 0;
            background: #fafcff;
            padding: 10px 12px;
            border-radius: 10px;
        }
        .personal-item {
            flex: 1 1 200px;
        }
        .label {
            font-weight: 600;
            color: #1e3b5c;
            font-size: 15px;
            display: block;
            margin-bottom: 2px;
        }

        .value {
            font-size: 15px;
        }

        hr {
            border: 0;
            border-top: 1px dashed #b3c9df;
            margin: 12px 0 10px;
        }

        .mono {
            font-family: 'Courier New', monospace;
            background: #f3f6fb;
            padding: 2px 5px;
            border-radius: 4px;
            font-size: 13.5px;
        }

        /* имитация вставки изображения из doc (media/image1.png) — текстовая заглушка */
        .image-placeholder {
            display: inline-flex;
            align-items: center;
            background: #f0f2f5;
            border: 1px dashed #7f9fbb;
            border-radius: 12px;
            padding: 4px 15px 4px 8px;
            margin-left: 10px;
            font-size: 13px;
            color: #2d4968;
        }
        .image-placeholder::before {
            content: "🖼️";
            margin-right: 6px;
            font-size: 16px;
            opacity: 0.7;
        }
    </style>
</head>
<body>
    <div class="resume">
        <!-- заголовок с именем и датой рождения (точно по тексту) -->
        <div class="fullname">
            Бородина Дарья Алексеевна
            <span>30.10.2005</span>
        </div>

        <!-- Образование + картинка-плейсхолдер (из .doc) -->
        <div class="section">
            <div class="section-title">Образование</div>
            <div class="education-detail" style="display: flex; flex-wrap: wrap; align-items: center; gap: 10px;">
                <span class="univ-name">Санкт-Петербургский Государственный Университет Аэрокосмического Приборостроения (ГУАП)</span>
                <!-- плейсхолдер для вставки рисунка из задания (image1) -->
                <span class="image-placeholder" style="width: auto; height: 0.8in;">Picture background media/image1.png</span>
            </div>
            <div class="univ-meta">
                <span><strong>Направление:</strong> 27.03.04 — Управление и информатика в технических системах</span>
            </div>
            <div class="period-badge">📅 Период обучения: 01.09.2023 – 31.08.2027 • 3-й курс, бакалавриат, очная форма</div>
        </div>

        <!-- Программное обеспечение и языки программирования (две колонки хорошо) -->
        <div class="two-col">
            <div class="section">
                <div class="section-title">Владение ПО</div>
                <div class="skills-cloud">
                    <span class="skill-tag">Matlab/Simulink</span>
                    <span class="skill-tag">Mathcad</span>
                    <span class="skill-tag">Multisim</span>
                    <span class="skill-tag">SimInTech</span>
                    <span class="skill-tag">SMathStudio</span>
                    <span class="skill-tag">КОМПАС-3D</span>
                    <span class="skill-tag">Access</span>
                    <span class="skill-tag">Excel</span>
                    <span class="skill-tag">Word</span>
                    <span class="skill-tag">PowerPoint</span>
                    <span class="skill-tag">Linux</span>
                </div>
            </div>
            <div class="section">
                <div class="section-title">Языки программирования</div>
                <div class="skills-cloud">
                    <span class="skill-tag skill-tag-alt">C</span>
                    <span class="skill-tag skill-tag-alt">C++</span>
                    <span class="skill-tag skill-tag-alt">Python</span>
                    <span class="skill-tag skill-tag-alt">C#</span>
                    <span class="skill-tag skill-tag-alt">Кумир</span>
                </div>
            </div>
        </div>

        <!-- ТАУ — большой блок с навыками (сокращённо, но детально) -->
        <div class="section">
            <div class="section-title">Теория автоматического управления (ТАУ)</div>
            <ul class="compact-list" style="display: grid; grid-template-columns: repeat(2,1fr); gap: 2px 15px;">
                <li>Математическое моделирование САУ</li>
                <li>Преобразования Лапласа</li>
                <li>Годографы, частотные характеристики (ЛАЧХ, ЛФЧХ, АФЧХ)</li>
                <li>Оценка устойчивости, нули и полюса</li>
                <li>Критерии: Найквиста, Михайлова, Ляпунова</li>
                <li>Матрица Гурвица, пространство состояний</li>
                <li>Накопленная ошибка, ПИД-регулятор</li>
                <li>Эквивалентные передаточные функции, свёртывание схем</li>
                <li>Частотный синтез корректирующего устройства</li>
                <li>Преобразование структурных схем</li>
            </ul>
        </div>

        <!-- Программирование логических схем и прочее -->
        <div class="two-col">
            <div class="section">
                <div class="section-title">Логические интегральные схемы</div>
                <div style="background:#f6faff; padding:8px 12px; border-radius:8px;">
                    <span style="font-weight:500;">▶ построение 4-х разрядного сумматора в пакете Multisim</span>
                </div>
            </div>
            <div class="section">
                <div class="section-title">Увлечения / предметы</div>
                <div class="skills-cloud">
                    <span class="skill-tag" style="background: #f0eef5;">ТДСУ</span>
                    <span class="skill-tag" style="background: #f0eef5;">ТАУ</span>
                </div>
            </div>
        </div>

        <!-- Контактные данные + готовность к практике и командировкам (связь со мной) -->
        <div class="contact-row">
            <span class="contact-item"><i>📞</i> +7-951-422-12-23</span>
            <span class="contact-item"><i>✉️</i> borodina_dasha05@mail.ru</span>
            <span class="contact-item"><i>📅</i> Практика: Июль</span>
            <span class="contact-item"><i>🚫</i> Командировки: нет</span>
        </div>

        <!-- блок: практика, английский, навыки личные качества — компактно -->
        <div style="display: flex; flex-wrap: wrap; gap: 25px; align-items: flex-start;">
            <!-- левая мини-колонка: английский и личные качества -->
            <div style="flex: 1.5; min-width: 200px;">
                <div style="margin-bottom: 10px;">
                    <span class="label">Уровень английского:</span>
                    <span class="value" style="background: #d9e7f5; padding:2px 12px; border-radius:20px;">B2</span>
                </div>
                <div>
                    <span class="label">Личные качества:</span>
                    <div style="display: flex; flex-wrap: wrap; gap: 6px; margin-top: 4px;">
                        <span class="skill-tag" style="background: #e2eaf3;">усердие и трудолюбие</span>
                        <span class="skill-tag" style="background: #e2eaf3;">быстрая обучаемость</span>
                        <span class="skill-tag" style="background: #e2eaf3;">стремление к сложной математике</span>
                    </div>
                </div>
            </div>
            <!-- правая часть: "Рассматриваю практику, готовности" и уточнение про месяцы (уже упомянуто в контактах, но продублируем по тексту) -->
            <div style="flex: 1;">
                <div style="background: #f8f5f0; padding: 8px 15px; border-radius: 24px;">
                    <span style="font-weight:600;">🔍 Рассматриваю практику</span>, готовности
                    <div style="font-size:14px; margin-top:4px;">📆 Месяцы для прохождения практики: <strong>Июль</strong></div>
                </div>
            </div>
        </div>

        <!-- небольшая черта и ещё раз деталь владения ПО, английский уже указан, но можно показать "Владение программным обеспечением" вторично? в исходном doc есть фраза повторно, но мы вынесли. добавим просто дополнительную строку навыки если нужно — но для точности повторим "Владение программным обеспечением" заголовок? Лучше не дублировать, но текст требует "Владение программным обеспечением Уровень Английский: B2 Навыки:" — стилизуем ниже -->
        <hr>
        <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap;">
            <div><span class="label">Владение программным обеспечением</span> <span class="mono">(подробно выше)</span></div>
            <div><span class="label">Английский B2</span> <span style="margin-left:15px;" class="label">Навыки:</span> <span class="mono">ТАУ, схемотехника, алгоритмы</span></div>
        </div>

        <!-- финальный блок: Связь со мной, готовности — продублировано почти всё, но для соблюдения полноты текста разместим внизу мелким шрифтом исходную фразу -->
        <div style="margin-top: 16px; font-size: 13px; color: #38658f; background: #f3f7fd; padding: 8px 12px; border-radius: 30px; display: flex; gap: 20px; flex-wrap: wrap;">
            <span>📱 +7-951-422-12-23</span>
            <span>📧 borodina_dasha05@mail.ru</span>
            <span>🎓 Рассматриваю практику, готовности • Готовность к командировкам: нет</span>
            <span>🗓️ Практика: Июль</span>
        </div>

        <!-- дополнительная строка из исходного текста: "Владение программным обеспечением Уровень Английский: B2 Навыки:" — уже есть, но зафиксируем почти дословно -->
        <div style="font-size: 13.5px; color: #2b4d6a; margin-top: 10px; border-left: 4px solid #b0c7dd; padding-left: 12px;">
            ⚙️ <strong>Владение программным обеспечением</strong> • Уровень Английский: B2 • <strong>Навыки:</strong> ТАУ, логические схемы, C/Python, Matlab.
        </div>

        <!-- также из оригинального текста осталась фраза "Навыки: ... Личные качества:" полностью покрыты -->
    </div>
    <!-- небольшой футер (для цифровой версии) -->
    <div style="text-align: center; font-size: 10px; margin-top: 5px; color: #aaa; display: none;">резюме А4</div>
</body>
</html>
