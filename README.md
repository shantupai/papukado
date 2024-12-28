# papukado
-1 going for a jog now
-1 making food and cleaning the house


def update_total():
    with open('rafafa.txt', 'r+') as file:
        lines = file.readlines()
        # הסרת שורת הסיכום אם קיימת
        if lines and lines[-1].startswith("Total:"):
            lines = lines[:-1]
        # חישוב הסכום
        total = sum(int(line.split()[1]) for line in lines if line.strip())
        # הוספת שורת סיכום
        lines.append(f"Total: {total}\n")
        # כתיבה חזרה לקובץ
        file.seek(0)
        file.writelines(lines)
        file.truncate()

if __name__ == "__main__":
    update_total()