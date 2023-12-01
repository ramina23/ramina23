from pptx import Presentation
from pptx.util import Inches
from fpdf import FPDF

# Создание объекта презентации
prs = Presentation()

# Создание нового слайда и добавление текста на каждый слайд
for i in range(15):
    slide_layout = prs.slide_layouts[1]  # Выберите макет слайда (1 = макет заголовка и содержания)
    slide = prs.slides.add_slide(slide_layout)
    title = slide.shapes.title
    content = slide.placeholders[1]

    title.text = f"Слайд {i+1}"
    content.text = f"Содержание модуля {i+1}"

# Сохранение презентации в файл pptx
prs.save("презентация.pptx")

# Конвертация презентации в PDF
pdf = FPDF()
slide_width = 11.69  # Ширина страницы A4 в дюймах (8.27 x 11.69 дюймов)
slide_height = 8.27  # Высота страницы A4 в дюймах
pdf.set_auto_page_break(auto=True, margin=15)  # Автоматический перенос текста на следующую страницу
pdf.set_font("Arial", size=12)

# Чтение каждого слайда из файла pptx и добавление его в PDF
for i in range(15):
    pdf.add_page()
    pdf.cell(slide_width, slide_height, txt=f"Слайд {i+1}", align="C")
    pdf.multi_cell(slide_width, 0.4, txt=f"Содержание модуля {i+1}", align="L")

# Сохранение презентации в PDF
pdf.output("презентация.pdf")
