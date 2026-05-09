# מדריך יפן - AI Agent README

## 📋 רקע והקשר

פרויקט זה מכיל אוסף של המלצות, טיפים ומידע מעשי לטיול ביפן. המידע נאסף מ:
- צילומי מסך מקבוצות WhatsApp ורשתות חברתיות
- חוויות אישיות מהטיול
- המלצות מקומיות ותיירים

### קהל יעד
- מטיילים ביפן (בעיקר מישראל)
- אנשים עם רגישות לגלוטן (ללא גלוטן)
- משפחות עם ילדים

## 🏗️ ארכיטקטורה

```
japan-trip-guide/
├── index.html         # Single Page Application - כל התוכן כאן
├── images/           # תמונות וצילומי מסך
└── README-AI.md      # תיעוד ל-AI
```

### טכנולוגיות
- **HTML5** - מבנה הדף
- **CSS3** - עיצוב (Bootstrap 5 + custom)
- **JavaScript (Vanilla)** - לוגיקה (ללא frameworks)
- **Font Awesome** - אייקונים
- **Google Maps** - קישורים למפות

### מגבלות
- ❌ אין Database
- ❌ אין Backend
- ❌ אין CMS
- ✅ Static HTML only - קל לעריכה ולhosting

### אחסון
- GitHub Pages - גיבוי והפצה
- OneDrive - גיבוי מקומי

## 📁 מבנה הקבצים

### index.html (פרטים)
- **Header** - כותרת ראשית + תיאור
- **Navigation** - תפריט ניווט מהיר
- **Search** - חיפוש בכל התוכן
- **City Boxes** - כל עיר = קופסה נפתחת:
  - תיאור קצר
  - אטרקציות
  - מסעדות (עם כתובות + קישורים)
  - קניות
  - טיפים
- **Photos Section** - גלריית צילומי מסך
- **Stats** - סטטיסטיקות
- **Modals**:
  - Lightbox לתמונות
  - Contact modal לפרטי מסעדות

### images/
- כל התמונות וצילומי המסך
- קבצים: `000000XX-PHOTO-*.jpg`

## 🔧 איך לערוך

### 1. הוספת עיר חדשה
```html
<div class="city-box" id="city-name">
    <div class="city-header" onclick="toggleCity('city-name')">
        <h2><i class="fas fa-icon"></i> שם העיר</h2>
    </div>
    <div class="city-content">
        <div class="city-desc"><p>תיאור קצר...</p></div>
    </div>
</div>
```

### 2. הוספת מסעדה
ב-index.html, בקטגוריית המסעדות:
```html
<div class="food-item">
    <strong style="cursor:pointer; color:#c0392b;" onclick="showContact('שם')">שם</strong>
    <span>תיאור</span><br><small>📍 כתובת</small>
</div>
```

וגם הוספה לאובייקט `contacts` ב-JavaScript.

### 3. הוספת טיפ
בקטגוריית "טיפים כלליים":
```html
<div class="tip-card">
    <h4>🔤 כותרת</h4>
    <p>תוכן...</p>
</div>
```

### 4. הוספת תמונה
```html
<div class="photo-item" style="position:relative;">
    <img src="images/שם.jpg" onclick="openLightbox(this.src)">
    <!-- ✓ אם יש טיפ מהתמונה -->
    <span style="position:absolute; background:#27ae60;">✓</span>
</div>
```

### 5. עדכון סטטיסטיקות
בקטגוריית "סטטיסטיקה":
```html
<div class="stat-item"><strong>מספר</strong><span>תיאור</span></div>
```

## ⚙️ פונקציות JavaScript

| פונקציה | תיאור |
|---------|--------|
| `toggleCity(id)` | פותח/סוגר קטגוריה |
| `openCity(id)` | פותח וגולל לקטגוריה |
| `showContact(name)` | מציג פרטי קשר של מסעדה |
| `openLightbox(src)` | מציג תמונה בגודל מלא |
| `closeLightbox()` | סוגר lightbox |
| `search(query)` | מחפש בתוכן |

## 🎨 עיצוב

### צבעים ראשיים
- אדום: `#c0392b` (כותרות, כפתורים)
- כחול: `#3498db` (קישורים)
- ירוק: `#27ae60` (מעובד/אישור)
- צהוב: `#ffeaa7` (רקע ניווט)

### עקרונות
- RTL - כיוון ימין לשמאל (עברית)
- Responsive - עובד במובייל
- Collapsible - קופסאות נפתחות/נסגרות

## 📝 הערות חשובות

1. **תמיד בקש אישור לפני commit ו-push**
2. הקבצים מיועדים ל-GitHub Pages
3. כל המסעדות עם כתובת - ניתן ללחוץ לפרטים
4. תמונות עם ✓ עברו עיבוד (יש טיפ מופק)
5. שמור על מבנה תגיות תקין

## 🚀 Deployment

```bash
git add .
git commit -m "תיאור שינויים"
git push origin main
```

האתר יהיה זמין בגיטהאב פייג'ס לאחר ה-push.

## 📞 קישורים שימושיים

- [Font Awesome](https://fontawesome.com)
- [Bootstrap 5](https://getbootstrap.com)
- [Google Maps](https://www.google.com/maps)