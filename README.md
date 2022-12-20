##  محتوى اليوم الثاني

محتوى الملف:

- ما هي TypeScript
- تثبيت وإعداد  TypeScript
- أهم مزايا TypeScript 



## ما هي TypeScript

ال JavaScript هي لغة مفتوحة المصدر وهي مجموعة شاملة من TypeScript
- يقدم ميزات اضافة لجافا سكربت بما في ذالك الانواع الثابتة 
- استخدام الانواع اختياري تماما
- ال  compiles down to regular JS
- يمكن استخدام الواجهة الامامية لـJS بالاضافة الى الواجهة الخلفية مع Node.js
- يتضمن معظم المميزات من ES6 و ES7 (الفئات ووظائف الاسهم وما الى ذالك)
- يمكن اضافة انواع من مكتبات الجهات الخارجية مع تعريفات النوع





## ال Dynamic VS Static Typing

- في اللغات   Dynamic Typed ، ترتبط الأنواع بقيم وقت التشغيل ولا يتم تسميتها صراحة في التعليمات البرمجية الخاصة بك
-  في  اللغات Static Typed ، تقوم بشكل صريح بتعيين أنواع للمتغيرات function parameters , وقيم الارجاع وما الى ذالك
- أمثلة على الديناميك (Java,C,C++,Rust,Go)
- امثلة على الثاتب (JavaScript, Python ,Ruby , PHP)



## ال Compiling TypeScript
- يستخدم TypeScript ملحقات .ts و. tx
- يستخدم TSC (compile   TypeScript) لترجمة ملفات .ts وصولاً إلى JS
- يمكن مشاهدة الملفات والإبلاغ عن الأخطاء في compile time
- تتضمن العديد من الأدوات تجميع TS بشكل افتراضي
- تتمتع معظم IDEs بدعم كبير لـ TS 
- يتم استخدام ملف tsconfig.json لتكوين طريقة عمل TypeScript

## تثبيت وإعداد TypeScript

يتم تثبيت تايب سكريبت عن طريق مدير الحزم NPM كما يلي:

      npm install -g typescript

البارامتر -g يعني بأننا قمنا بتثبيت الحزمة بشكل عام() في جهازنا ومن الممكن استخدامها والوصول إليها من أي مشروع أو مجلد وليس المشروع الحالي فقط.

سنقوم باختبار تايب سكريبت عن طريق الكود أسفله، والذي كما تلاحظون هو مجرد كود جافا سكريبت اعتيادي، ولكنه موجود في ملف امتداده .ts وليس .js.



##### يتم اضافة tsconfig.json  بألامر التالي

     tsc --init
     
```diff
! يجب استخدام tsc  ملحقاتها  في  Command  لتجنب الاخطاء 
```


## أهم مزايا TypeScript

1. دعم الأنواع

- لغات تتحقق من أنواع المتغيرات خلال مرحلة الترجمة أو Compilation، ولذلك يسمى دعمها للأنواع بالدعم الستاتيكي أو الصريح (Static Type Checking). من هذه اللغات نجد جافا، ++C و Go. عندما تصادف هذه اللغات خطأ متعلق بنوع المتغير في الكود فإن الترجمة تفشل ولا تتم بنجاح.

- وصنف آخر من اللغات يقوم بالتحقق من أنواع المتغيرات بشكل ديناميكي (Dynamic Type Checking) أثناء تشغيل البرنامج، ومن هذا الصنف نجد جافا سكريبت، بايثون و PHP.

## الأنواع المدعومة من طرف TypeScript

 بالإضافة لنوع String  تدعم لغة تايب سكريبت عددا من الأنواع الأخرى ونذكر منها أهمها:

#### Boolean

يستخدم هذا النوع للتأكد من أن المتغير هو فعلا Boolean ويقبل إحدى القيمتين true أو false.
  
     let myBool: boolean = false;
     
#### Number

جميع الأعداد الصحيحة (Integers) والعشرية (Decimal) يعتبرها TypeScript من نوع Number، ويضيف إليها كذلك الأعداد من أنظمة Octal ،Hexadecimal و Binary. هذين الأخيرين مدعومين كذلك في جافا سكريبت في الإصدار ES6.

      let intNumber: number = 6;
      let decNumber: number = 6.5;
      let hexNumber: number = 0xf00d;
      let binaryNumber: number = 0b1010;
      let octalNumber: number = 0o744;
      
      
 #### Array
 
 يدعم كذلك تايب سكريبت نوع المصفوفات، ويمكن التصريح بهذا النوع من المتغيرات بطريقتين مختلفتين:
 
 - الطريقة الأولى

        let list: number[] = [1, 2, 3];
         

نلاحظ أننا استعملنا الكلمة number وأمامها معقوفتين [] لكي نخبر تايب سكريبت بأننا أولا نريد مصفوفة وثانيا نريد من هذه المصفوفة أن تحتوي على أعداد فقط.


-الطريقة الثانية

        let list: Array<number> = [1, 2, 3];


#### إذا أردنا مصفوفة عشوائية، بأنواع مختلطة نستعمل النوع any:

        let list: any[] = [1, 'hello', true];

 #### Any
 
 هذا النوع فريد من نوعه مقارنة بالأنواع الأخرى. عن طريقه نرسل رسالة لمترجم تايب سكريبت بأننا غير متأكدين من نوع أو طبيعة المتغير، وأن الأخير قد يكون من أي نوع كان بحسب القيمة المسندة إليه.
 
 يمكن النظر إلى any على أنه الأقرب إلى آلية Dynamic Typing التي تنهجها لغة البرمجة جافا سكريبت نفسها.

      let notSure: any = 5;
      notSure = 'hello world'; // Ok
      notSure = false; // Ok
      
 #### بالإضافة إلى ما ذكرناه، هناك مجموعة من الأنواع الأخرى:

- ال Tuple
- ال Enum
- ال Void
- ال Null and Undefined
- ال Never
- ال Object

تفاصيل وشرح لجميع الأنواع تجدونها على في [ هذا الرابط](https://www.typescriptlang.org/docs/handbook/basic-types.html)

## 2. الدوال في TypeScript

ضيف لغة TypeScript مجموعة من المميزات للدوال، فإلى جانب تحديد نوع البارامترات الذي اكتشفناه أعلاه، يمكننا كذلك تحديد نوع القيمة المرجعة من طرف الدالة

        function greeter(name: string): string {
          return 'Hello, ' + name;
        }

## 3. الواجهات (Interfaces)

تتيح لنا الواجهات تعيين الخصائص والوظائف الواجب توفرها في كائن (Object) أو صنف (Class) محدد.


نقوم بالتصريح بالواجهة في TypeScript بهذه الطريقة:



      interface Person {
        firstName: string;
        lastName: string;
      }
      
ويمكننا استخدامها تماما مثلما نستعمل الأنواع الأساسية المدعومة من لغة البرمجة Typescript.


      function greeter(person: Person) {
        return 'Hello, ' + person.firstName + ' ' + person.lastName;
      }
      
يمكن للكائن person هنا أن يحتوي على خاصيات إضافية ولكن من الضروري أن يتوفر على الأقل على الخاصيتين firstName و lastName المصرح بهما في واجهة Person.

      interface Person {
        firstName: string;
        lastName: string;
        getFullName(): string;
      }
      class Student implements Person {
        constructor(public firstName: string, public lastName: string) {}

        getFullName() {
          return this.firstName + ' ' + this.lastName;
        }
      }

      var student = new Student('Aissa', 'BOUGUERN');

      console.log(student.getFullName()); // Aissa BOUGUERN
      
لاحظوا أننا استعملنا الكلمة implements لنطلب من الصنف Student اتباع بنية الواجهة Person.

