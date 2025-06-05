<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>لوحة المدير | إدارة البرامج وأنواع الغذاء</title>
    <style>
        body { font-family: 'Tajawal', Arial, sans-serif; background: #f7f7f7; }
        .container { max-width: 1200px; margin: 40px auto; background: #fff; padding: 40px; border-radius: 16px; box-shadow: 0 2px 16px #eee; }
        h1, h2, h3 { color: #276943; }
        .section { margin-bottom: 40px; }
        .btn { background: #276943; color: #fff; padding: 7px 18px; border: none; border-radius: 5px; cursor: pointer; font-size: 15px;}
        .btn:hover { background: #195132; }
        .table { width: 100%; border-collapse: collapse; margin-top: 18px;}
        .table th, .table td { border: 1px solid #ddd; padding: 8px; text-align: center;}
        .table th { background: #f0f0f0;}
        label { font-weight: bold; }
        input[type="text"], input[type="number"], select { padding: 6px; border-radius: 4px; border: 1px solid #ccc; }
        .actions button { margin: 0 2px; }
        .add-form { margin-top: 16px; margin-bottom: 16px; }
        .logo { width: 120px; margin-bottom: 20px;}
    </style>
</head>
<body>
    <div class="container">
        <img class="logo" src="logo.png" alt="شعار النظام">
        <h1>إدارة البرامج الغذائية وأنواع الغذاء</h1>

        <!-- إدارة البرامج الغذائية -->
        <div class="section">
            <h2>البرامج الغذائية</h2>
            <form class="add-form" onsubmit="event.preventDefault(); addDietProgram();">
                <label>اسم البرنامج الغذائي:</label>
                <input type="text" id="dietProgramName" required>
                <label>الوصف:</label>
                <input type="text" id="dietProgramDesc">
                <button class="btn" type="submit">إضافة</button>
            </form>
            <table class="table" id="dietProgramsTable">
                <tr>
                    <th>اسم البرنامج</th>
                    <th>الوصف</th>
                    <th>إجراءات</th>
                </tr>
                <tr>
                    <td>برنامج تخسيس</td>
                    <td>تقليل السعرات وخفض الوزن</td>
                    <td class="actions">
                        <button class="btn" onclick="editDietProgram()">تعديل</button>
                        <button class="btn" onclick="deleteDietProgram()">حذف</button>
                    </td>
                </tr>
                <!-- أضف المزيد -->
            </table>
        </div>

        <!-- إدارة أنواع الأغذية -->
        <div class="section">
            <h2>أنواع الأغذية</h2>
            <form class="add-form" onsubmit="event.preventDefault(); addFoodCategory();">
                <label>اسم النوع:</label>
                <input type="text" id="foodCategoryName" required>
                <button class="btn" type="submit">إضافة</button>
            </form>
            <table class="table" id="foodCategoriesTable">
                <tr>
                    <th>اسم النوع</th>
                    <th>إجراءات</th>
                </tr>
                <tr>
                    <td>بروتينات</td>
                    <td class="actions">
                        <button class="btn" onclick="editFoodCategory()">تعديل</button>
                        <button class="btn" onclick="deleteFoodCategory()">حذف</button>
                    </td>
                </tr>
                <tr>
                    <td>نشويات</td>
                    <td class="actions">
                        <button class="btn" onclick="editFoodCategory()">تعديل</button>
                        <button class="btn" onclick="deleteFoodCategory()">حذف</button>
                    </td>
                </tr>
                <!-- أضف المزيد -->
            </table>
        </div>

        <!-- إدارة عناصر الغذاء -->
        <div class="section">
            <h2>محتويات الغذاء (العناصر الغذائية)</h2>
            <form class="add-form" onsubmit="event.preventDefault(); addFoodItem();">
                <label>اسم العنصر:</label>
                <input type="text" id="foodItemName" required>
                <label>النوع:</label>
                <select id="foodItemCategory">
                    <option>بروتينات</option>
                    <option>نشويات</option>
                    <option>خضار</option>
                    <option>فواكه</option>
                    <!-- أضف المزيد -->
                </select>
                <label>سعرات (كالوري):</label>
                <input type="number" id="foodItemCalories" step="0.01" required>
                <label>بروتين (غ):</label>
                <input type="number" id="foodItemProtein" step="0.01">
                <label>كارب (غ):</label>
                <input type="number" id="foodItemCarb" step="0.01">
                <label>دهون (غ):</label>
                <input type="number" id="foodItemFat" step="0.01">
                <button class="btn" type="submit">إضافة</button>
            </form>
            <table class="table" id="foodItemsTable">
                <tr>
                    <th>اسم العنصر</th>
                    <th>النوع</th>
                    <th>السعرات</th>
                    <th>البروتين</th>
                    <th>الكربوهيدرات</th>
                    <th>الدهون</th>
                    <th>إجراءات</th>
                </tr>
                <tr>
                    <td>صدر دجاج مشوي</td>
                    <td>بروتينات</td>
                    <td>165</td>
                    <td>31</td>
                    <td>0</td>
                    <td>3.6</td>
                    <td class="actions">
                        <button class="btn" onclick="editFoodItem()">تعديل</button>
                        <button class="btn" onclick="deleteFoodItem()">حذف</button>
                    </td>
                </tr>
                <!-- أضف المزيد -->
            </table>
        </div>
    </div>
    <script>
        // هذه فقط أمثلة توضيحية للعمليات ويمكن ربطها بالباك-إند لاحقاً
        function addDietProgram() { alert('إضافة برنامج غذائي (تجريبي)'); }
        function editDietProgram() { alert('تعديل البرنامج (تجريبي)'); }
        function deleteDietProgram() { if(confirm('حذف البرنامج؟')) alert('تم الحذف (تجريبي)'); }
        function addFoodCategory() { alert('إضافة نوع غذاء (تجريبي)'); }
        function editFoodCategory() { alert('تعديل النوع (تجريبي)'); }
        function deleteFoodCategory() { if(confirm('حذف النوع؟')) alert('تم الحذف (تجريبي)'); }
        function addFoodItem() { alert('إضافة عنصر غذائي (تجريبي)'); }
        function editFoodItem() { alert('تعديل العنصر (تجريبي)'); }
        function deleteFoodItem() { if(confirm('حذف العنصر؟')) alert('تم الحذف (تجريبي)'); }
    </script>
</body>
