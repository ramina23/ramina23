from pptx import Presentation

# Создание новой презентации
presentation = Presentation()

# Slide 1
slide = presentation.slides.add_slide(presentation.slide_layouts[0])
title = slide.shapes.title
title.text = "Тема: Реализация содержания всех модулей в практике работы современной школы в соответствии с требованиями ФГОС ОО 2022"

# Slide 2
slide = presentation.slides.add_slide(presentation.slide_layouts[1])
title = slide.shapes.title
title.text = "Содержание"
content = slide.shapes.add_textbox(left=0, top=0, width=9144000, height=6858000).text_frame
content.text = "1. Введение\n2. Модуль 1: ...\n3. Модуль 2: ...\n4. Модуль 3: ...\n5. Модуль 4: ...\n6. Модуль 5: ...\n7. Модуль 6: ...\n8. Модуль 7: ...\n9. Модуль 8: ...\n10. Модуль 9: ...\n11. Модуль 10: ...\n12. Заключение\n13. Вопросы и ответы\n14. Ссылки\n15. Спасибо!"

# Slide 3-13
for i in range(3, 14):
    slide = presentation.slides.add_slide(presentation.slide_layouts[1])
    title = slide.shapes.title
    title.text = f"Модуль {i-2}: Название модуля"
    content = slide.shapes.add_textbox(left=0, top=0, width=9144000, height=6858000).text_frame
    content.text = f"Описание модуля {i-2}: ..."

# Slide 14
slide = presentation.slides.add_slide(presentation.slide_layouts[1])
title = slide.shapes.title
title.text = "Заключение"
content = slide.shapes.add_textbox(left=0, top=0, width=9144000, height=6858000).text_frame
content.text = "Суммируя все, реализация содержания всех модулей в практике работы современной школы в соответствии с требованиями ФГОС ОО 2022 является ключевым фактором успешного обучения и развития учеников."

# Slide 15
slide = presentation.slides.add_slide(presentation.slide_layouts[1])
title = slide.shapes.title
title.text = "Вопросы и ответы"
content = slide.shapes.add_textbox(left=0, top=0, width=9144000, height=6858000).text_frame
content.text = "Здесь могут быть размещены вопросы и ответы, связанные с реализацией содержания всех модулей в практике работы современной школы."

# Сохранение презентации
presentation.save("Реализация_содержания_школьных_модулей.pptx")
