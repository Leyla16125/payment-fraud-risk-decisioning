# Ödənişlərdə Fraud Aşkarlanması və Risk Qərarlarının İdarə Edilməsi

**Project:** Payment Fraud & Risk Decisioning Platform  
**Status:** Planning

## 1. Biznes Problemi

Banklar və ödəniş xidməti göstərən şirkətlər üçün əsas çətinliklərdən biri dələduzluq ehtimalı olan əməliyyatları vaxtında müəyyənləşdirməkdir. Bütün əməliyyatları əl ilə yoxlamaq mümkün olmadığından hansı əməliyyatların daha çox diqqət tələb etdiyini müəyyənləşdirmək vacibdir.

Bu prosesdə iki əsas problem yaranır. Fraud əməliyyatı aşkarlanmadıqda maliyyə itkisi baş verə bilər. Digər tərəfdən, qanuni əməliyyatın səhvən fraud hesab edilməsi müştərinin ödəniş edə bilməməsinə, narazılığa və əlavə araşdırma xərclərinə səbəb ola bilər.

Layihənin məqsədi ödəniş məlumatlarını Machine Learning ilə təhlil edərək şübhəli əməliyyatları müəyyənləşdirmək və onların risk səviyyəsinə əsasən prioritetləşdirilməsini təmin etməkdir.

Burada əsas diqqət yalnız mümkün qədər çox fraud hadisəsi tapmağa deyil, həm də məhdud araşdırma imkanlarından səmərəli istifadə etməyə və yanlış qərarların maliyyə təsirini qiymətləndirməyə yönələcək.

## 2. Hədəf İstifadəçilər və Maraqlı Tərəflər

Platforma əsasən bankların və fintech şirkətlərinin fraud və risk komandalarının iş prosesləri nəzərə alınaraq hazırlanacaq.

**Fraud Analyst:** Şübhəli əməliyyatları araşdıran əməkdaşdır. Sistem ona risk səviyyəsi yüksək olan əməliyyatları müəyyənləşdirməyə və araşdırmaları prioritetləşdirməyə kömək etməlidir.

**Risk Manager:** Fraud nəticəsində yarana biləcək itkiləri və tətbiq olunan qərar qaydalarının nəticələrini qiymətləndirir. Onun üçün yalnız aşkarlanan fraud sayı deyil, səhv qərarların xərci də əhəmiyyətlidir.

**Bank və fintech şirkətləri:** Fraud itkilərini azaltmaqla yanaşı, qanuni ödənişlərin lazımsız yerə bloklanmamasında maraqlıdırlar.

**Müştərilər və ödəniş qəbul edən şirkətlər:** Ödənişlərin təhlükəsiz, eyni zamanda mümkün qədər problemsiz həyata keçirilməsini gözləyirlər.

**ML Engineer və Model Validator:** Modelin necə işlədiyini, hansı məlumatlardan istifadə etdiyini, nəticələrinin nə dərəcədə etibarlı olduğunu və hansı məhdudiyyətlərə sahib olduğunu qiymətləndirirlər.

## 3. Layihənin Əhatə Dairəsi

Layihənin ilkin versiyası kartla aparılan ödəniş əməliyyatlarına fokuslanacaq.

Əsas məqsəd ödənişin fraud olub-olmadığını proqnozlaşdıran model hazırlamaqla kifayətlənməmək, həmin proqnozun əməliyyat qərarlarında necə istifadə oluna biləcəyini də göstərməkdir.

**Layihə çərçivəsində nəzərdə tutulan işlər:**

- Ödəniş məlumatlarının araşdırılması və model üçün hazırlanması.
- Əməliyyat tarixçəsindən istifadə etməklə əlavə xüsusiyyətlərin yaradılması (*Feature Engineering*).
- Fraud riskini qiymətləndirən ML modelinin hazırlanması.
- Sadə qaydalara əsaslanan yanaşma ilə ML nəticələrinin müqayisəsi.
- Risk Score və mümkün maliyyə itkisi əsasında əməliyyatların prioritetləşdirilməsi.
- Məhdud araşdırma imkanları nəzərə alınmaqla qərar qaydalarının simulyasiyası.
- Modelin nəticələrini göstərən sadə istifadəçi interfeysi.
- Modelin qiymətləndirilməsi, test edilməsi və məhdudiyyətlərinin sənədləşdirilməsi.

Platforma real bank sistemlərinə qoşulmayacaq və həqiqi kart əməliyyatlarını idarə etməyəcək. Bütün qərarlar mövcud məlumatlar üzərində aparılan analiz və simulyasiyalara əsaslanacaq.

AML/KYC, müştəri identifikasiyası və real ödənişlərin avtomatik bloklanması layihənin əhatə dairəsinə daxil deyil.

## 4. Təklif Olunan Qərar Qəbulu Prosesi

Sistemin iş prinsipi bir neçə mərhələdən ibarət olacaq.

Əvvəlcə ödəniş əməliyyatı haqqında mövcud məlumatlar modelə ötürüləcək. Model əməliyyatın xüsusiyyətlərini və əvvəlki məlumatlardan öyrəndiyi nümunələri nəzərə alaraq Fraud Risk Score hesablayacaq.

Daha sonra bu nəticə *Risk Decision Engine* tərəfindən qiymətləndiriləcək. Burada əməliyyatın risk səviyyəsi ilə yanaşı, mümkün maliyyə itkisi və fraud komandasının araşdırma imkanları da nəzərə alınacaq.

Nəticədə əməliyyat üç kateqoriyadan birinə aid edilə bilər:

- **Approve:** Əməliyyatın təsdiqlənməsi tövsiyə olunur.
- **Review:** Əməliyyatın əlavə araşdırmaya göndərilməsi tövsiyə olunur.
- **Block:** Mövcud qərar siyasətinə əsasən bloklama tövsiyəsi verilir.

Bu qərarlar real ödənişlərə tətbiq edilməyəcək. Məqsəd müxtəlif qərar qaydalarının nəticələrini müqayisə etməkdir.

Məsələn, yalnız Fraud Risk Score-a əsaslanan yanaşma ilə mümkün maliyyə itkisini də nəzərə alan yanaşmanın eyni əməliyyatlar üzərində necə fərqli nəticələr verdiyi yoxlanılacaq.

## 5. Uğur Göstəriciləri

Layihənin nəticələrini yalnız modelin neçə əməliyyatı düzgün təsnif etməsi ilə qiymətləndirmək kifayət deyil. Fraud əməliyyatları ümumi ödənişlərin kiçik hissəsini təşkil edə bildiyindən yüksək Accuracy göstəricisi yanıltıcı ola bilər.

Buna görə qiymətləndirmədə aşağıdakı göstəricilərdən istifadə olunması nəzərdə tutulur:

| Göstərici | Nəyi ölçür? |
|---|---|
| Recall | Həqiqi fraud əməliyyatlarının hansı hissəsinin aşkarlandığını |
| Precision | Fraud kimi işarələnmiş əməliyyatların hansı hissəsinin həqiqətən fraud olduğunu |
| PR-AUC / Average Precision | Müxtəlif qərar hədlərində precision və recall nəticələrini |
| Recall at Review Capacity | Məhdud araşdırma imkanı daxilində neçə fraud əməliyyatının aşkarlandığını |
| False Positive Rate | Qanuni əməliyyatların hansı hissəsinin səhvən şübhəli hesab edildiyini |
| Estimated Business Cost | Müəyyən edilmiş xərc fərziyyələri əsasında qərarların maliyyə nəticəsini |

Model əvvəlcə sadə bir baseline ilə müqayisə olunacaq. Daha mürəkkəb yanaşmanın üstünlüyü yalnız test nəticələri bunu göstərdiyi halda qəbul ediləcək.

Layihənin əsas qiymətləndirmə suallarından biri belə olacaq:

**Eyni araşdırma imkanı daxilində yalnız fraud riskinə əsaslanan seçim, yoxsa potensial maliyyə itkisini də nəzərə alan seçim daha yaxşı nəticə verir?**

Bu suala cavab vermək üçün hər iki yanaşma eyni test məlumatları və əvvəlcədən müəyyən edilmiş fərziyyələr əsasında müqayisə ediləcək.

## 6. Məlumatlarla Bağlı Fərziyyələr və Məhdudiyyətlər

Layihə üçün ilkin olaraq *Fraud Detection Handbook* tərəfindən təqdim olunan sintetik ödəniş məlumatları nəzərdən keçirilir.

Bu məlumatlarda əməliyyatın tarixi, məbləği, müştəri və terminal identifikatorları, həmçinin fraud olub-olmadığını göstərən məlumat mövcuddur.

Dataset-in üstünlüyü eyni müştərinin müxtəlif vaxtlarda etdiyi ödənişləri analiz etməyə imkan verməsidir. Bu məlumatlardan istifadə etməklə əməliyyatların tezliyi, əvvəlki məbləğlərlə fərqi və digər davranış xüsusiyyətləri hesablana bilər.

Lakin məlumatlar real bank mühitindən götürülməyib. Fraud hadisələri simulatorun müəyyən etdiyi qaydalar əsasında yaradılır. Buna görə sintetik məlumatlarda yaxşı nəticə göstərən modelin real ödəniş sistemində də eyni performansa sahib olacağını iddia etmək olmaz.

Digər məhdudiyyət bankın həqiqi maliyyə xərcləri haqqında məlumatın olmamasıdır. Bu səbəbdən fraud itkiləri, yanlış bloklama və araşdırma xərcləri üçün istifadə ediləcək rəqəmlər ayrıca qeyd olunmuş fərziyyələrə əsaslanacaq.

Əlavə qiymətləndirmə üçün ULB Credit Card Fraud Detection dataset-indən istifadə imkanı da araşdırılacaq.

Dataset seçimi və istifadə şərtləri data audit mərhələsində dəqiqləşdiriləcək.

## 7. Layihənin Hazırkı Vəziyyəti

Layihə hazırda planlaşdırma mərhələsindədir. Əsas biznes problemi, nəzərdə tutulan istifadəçilər və ilkin funksiyalar müəyyənləşdirilib.

Növbəti mərhələdə dataset seçimi dəqiqləşdiriləcək, məlumatların strukturu araşdırılacaq və ilkin baseline üçün qiymətləndirmə planı hazırlanacaq.

ML modeli, Risk Decision Engine, API və istifadəçi interfeysi hələ implementasiya edilməyib.

Layihənin yekun nəticələri aparılacaq eksperimentlərdən asılı olacaq. Hazırkı mərhələdə konkret performans göstəricisi və ya maliyyə qənaəti iddia edilmir.

---

