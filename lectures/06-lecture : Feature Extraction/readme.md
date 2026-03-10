# 📚 Lec. 6: Feature Extraction

**Course:** Pattern Recognition  

---

# 1. Introduction to Feature Extraction

Feature Extraction (استخراج الخصائص) هو عملية استخراج **معلومات مهمة من البيانات الخام** لاستخدامها في التعلم الآلي أو التصنيف.

### Example

في **Image Recognition** بدل استخدام جميع البكسلات في الصورة:
Image → Pixels (1000+ values)

نستخرج خصائص مثل:

- Edges
- Textures
- Shapes

فتصبح البيانات:
Image → Features → Classifier

---

# 2. Feature Extraction Approaches

يمكن تقسيم طرق استخراج الخصائص إلى **4 أنواع رئيسية**:

1. Geometrical Feature Extraction  
2. Statistical Feature Extraction  
3. Transformational Feature Extraction  
4. Texture-Based Feature Extraction  

ثم يتم استخدام هذه الخصائص كمدخلات إلى
**Classifier** 
مثل:

- Neural Network
- Decision Tree

---

# a) Geometrical Feature Extraction

تعتمد هذه الطريقة على **شكل الجسم وحجمه والعلاقات المكانية**.

تستخدم كثيرًا في:

- Computer Vision
- Image Processing
- Object Detection

### Examples of Geometrical Features

- **Area** → مساحة الجسم  
- **Perimeter** → محيط الجسم  
- **Aspect Ratio** → نسبة العرض إلى الارتفاع  
- **Circularity** → مدى قرب الشكل من الدائرة  

### Example: Autonomous Driving

في السيارات ذاتية القيادة يتم استخراج خصائص مثل:

- Area
- Aspect Ratio
- Circularity

لتمييز:

| Object | Features |
|------|------|
| Vehicles | Large area + wide aspect ratio |
| Traffic Signs | Circular or rectangular |

هذا يساعد النظام على **التعرف على الأشياء بسرعة أثناء القيادة**.

---

# b) Statistical Feature Extraction

تعتمد هذه الطريقة على **الإحصائيات الخاصة بالبيانات**.

تستخدم في:

- Time Series Analysis
- Signal Processing
- Data Analysis

### Examples of Statistical Features

- **Mean** → المتوسط  
- **Median** → الوسيط  
- **Mode** → المنوال  

- **Variance** → التباين  
- **Standard Deviation** → الانحراف المعياري  

- **Skewness** → مدى انحراف التوزيع  
- **Kurtosis** → مدى تركّز القيم في الأطراف  

- **Correlation** → العلاقة بين المتغيرات

### Example: Medical Diagnosis

في نظام تشخيص طبي يتم تحليل بيانات المرضى مثل:

- Blood Pressure
- Heart Rate
- Cholesterol

ثم يتم استخراج خصائص مثل:

- Mean Blood Pressure
- Variance of Heart Rate
- Correlation between Cholesterol and Blood Pressure

هذه الخصائص تساعد في **توقع الأمراض مثل أمراض القلب أو السكري**.

---

# c) Transformational Feature Extraction

في هذه الطريقة يتم **تحويل البيانات إلى مجال مختلف** للحصول على معلومات أكثر فائدة.

تستخدم في:

- Signal Processing
- Image Analysis
- Audio Analysis

### Examples

**Fourier Transform**

يحول البيانات من:

Time Domain → Frequency Domain


**Wavelet Transform**

يعطي معلومات عن:

- الوقت
- التردد

**PCA (Principal Component Analysis)**

تستخدم لتقليل عدد الخصائص مع الحفاظ على أهم المعلومات.

---

### Example: Speech Recognition

في نظام التعرف على الكلام:

يتم تحويل الصوت باستخدام:

- Fourier Transform
- Wavelet Transform

لاستخراج **مكونات التردد** التي تمثل الأصوات المختلفة.

---

# d) Texture-Based Feature Extraction

تركز هذه الطريقة على **ملمس السطح أو النمط داخل الصورة**.

مثل:

- rough texture
- smooth texture
- repeated patterns

### Methods

- **GLCM (Gray Level Co-occurrence Matrix)**
- **LBP (Local Binary Patterns)**
- **Gabor Filters**

### Example: Satellite Image Analysis

في صور الأقمار الصناعية يمكن تمييز:

| Type | Texture |
|----|----|
| Forest | Rough texture |
| Urban | Regular patterns |
| Water | Smooth texture |

---

# Face Recognition Example

في نظام **التعرف على الوجوه** يتم دمج عدة أنواع من الخصائص.

### 1. Geometrical Features

- Distance between eyes
- Face aspect ratio
- Eye circularity

---

### 2. Statistical Features

- Mean pixel intensity
- Variance of facial regions

---

### 3. Transformational Features

باستخدام:


Fourier Transform


لاستخراج الأنماط في الوجه.

---

### 4. Texture Features

تحليل:

- Skin texture
- Hair patterns

دمج هذه الخصائص يساعد النظام على **التعرف على الأشخاص بدقة حتى مع اختلاف الإضاءة أو التعبير**.

---

# Principal Component Analysis (PCA)

PCA هي طريقة **لتقليل الأبعاد (Dimensionality Reduction)**.

كلما زاد عدد الخصائص:

- يزيد وقت التدريب
- تزيد الحسابات
- وقد تقل الدقة بعد نقطة معينة

لذلك نحاول اختيار **أفضل الخصائص فقط**.

---

# Dimensionality Reduction Methods

هناك طريقتان:

1. **Feature Extraction**
2. **Feature Selection**

---

# Feature Extraction vs Feature Selection

| Feature Extraction | Feature Selection |
|---|---|
| Creates new features | Selects existing features |
| Combines original data | Chooses the most important features |
| Example: PCA | Example: selecting best variables |

---

# How to Detect Unimportant Features

إذا كان لدينا بيانات طلاب مثل:

| ID | Name | Grade | Total |
|---|---|---|---|

فبعض الخصائص قد تكون **غير مهمة للتصنيف**.

مثال:


Hair type (thick / thin)


هذه الخاصية قد لا تؤثر على النتيجة.

---

# Rules to Remove Features

## Rule 1: Low Variance

إذا كان **التباين صغير جدًا**:


Variance ≈ 0


فالقيم متشابهة بين جميع العينات.

لذلك هذه الخاصية **غير مفيدة**.

---

## Rule 2: Linear Correlation

إذا كانت الخاصية مرتبطة خطيًا بميزة أخرى:


Z = aX + bY


فيمكن حذف إحداهما لأن الأخرى تعوضها.

---

# When Should a Feature be Kept?

## Rule 1: Independence

يجب أن تكون الخاصية **مستقلة عن الخصائص الأخرى**.

أي أن:


Covariance is small


---

## Rule 2: High Variance

إذا كانت الخاصية **تختلف بين الأشخاص أو العينات**.

مثال:


Student Grades


هذه خاصية مهمة لأنها تختلف بين الطلاب.

---

# Summary

في هذه المحاضرة تعلمنا:

- مفهوم **Feature Extraction**
- أنواع طرق استخراج الخصائص
- Geometrical features
- Statistical features
- Transformational features
- Texture features
- مفهوم **Dimensionality Reduction**
- الفرق بين **Feature Extraction و Feature Selection**
- كيفية اختيار الخصائص المهمة
