---
published: true
---
<h1>Buffer overflow</h1>
<p>
 
ما هو ال Buffer OverFlow ؟
بيحصل ال Buffer OverFlow لما حجم ال Data بيبقي اكبر من ال Storage Capacity بتاعت ال Memory Buffer 
أكيد انت هتسأل ايه هو ال Buffer ->
هو جزء من ال  Main Memory بيتسخدم في حفظ ال Data خلال عملية ال Input و ال Output , مفيد جدا في نقل ال Data بين ال Processes.
الي بيحصل بقي انك لو دخلت كم كبير من ال Data ال Buffer هيعمل Over write لل Data الموجودة 
طب تعالي نعرف بقي ال Buffer OverFlow attack ->
ال Attacker بيعمل FUZZ علي ال Application عشان يعرف مساحة تخزين الاوامر الي بيبعتها لل Memory و أول ما يوصل للجزء دا يبتدي يعمل ال Payload بتاعه عشان يخلي ال Application ينفذ اوامر تديله هو صلاحيات علي ال Machine أو يقدر انه ياخد ملفات Senstive و ممكن يأذي ال Enviroment كله. 
في نوعين لل Buffer OverFlow Attack :
1- Stack-based
وال Attack دا بيبقي علي ال Stack الموجودة في ال RAM 
طب ايه هو ال Stack ؟ 
ال Stack دا جزء موجود في ال Ram , وظيفته تنفيذ الاوامر بتاعت ال Application و بيكون LIFO يعني (Last In First Out ) يعني أخر أمر في الترتيب هو أول أمر بيتنفذ
2- Heap-based 
النوع دا أصعب بكتير من النوع الاول و دا بيتم علي ال Heap Memory 
ال Heap دي Memory بيستخدمها لغات البرمجة عشان تخزن ال Gloabl variables و دا بيكون By default
</p>
