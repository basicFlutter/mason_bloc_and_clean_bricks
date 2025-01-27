# قالب Mason برای معماری Clean و BLoC در Flutter

این قالب (brick) برای اوناییه که می‌خوان بدون دردسر و به صورت خودکار فایل‌ها و پوشه‌های مربوط به فیچرهای پروژه Flutter رو بسازن. با استفاده از این ابزار، می‌تونی با سرعت و نظم بیشتر کدنویسی کنی و ساختار پروژه‌ات همیشه استاندارد بمونه.

## چرا این قالب خیلی خفنه؟

### 🚀 ساخت خودکار همه چی برای یه پروژه
دیگه لازم نیست دستی بری پوشه درست کنی یا فایل بسازی. این قالب همه چی رو خودش برات مرتب و آماده می‌کنه. 😎

### ✨ معماری Clean
با این قالب، کدت تمیز، منظم و مقیاس‌پذیره. انگار داری برای آینده‌ات برنامه‌ریزی می‌کنی، چون ساختار پروژه‌ات همیشه قابل گسترشه.

### 🧩 همه چی آماده هست (BLoC، UseCase و Repository) 
همه لایه‌ها از هم جدا شدن. یعنی خیلی راحت‌تر می‌تونی منطق، داده‌ها و رابط کاربری رو مدیریت کنی.

### 📂 پوشه‌بندی تمیز و منعطف
همه چی سر جای خودشه و اگه بخوای گسترش بدی، هیچ مشکلی نداری. ساختار پروژه همیشه مرتب و خواناست.

### 🌐 پشتیبانی از چندزبانه بودن (Localization)
اگه می‌خوای برنامه‌ات چندزبانه باشه، این قالب بهت اجازه می‌ده راحت ترجمه‌های مختلف رو اضافه کنی و از کاربرهای مختلف پشتیبانی کنی.

### 🔔پشتیبانی از نوتیفیکیشن (Firebase Cloud Messaging)
برای ارسال و دریافت نوتیفیکیشن‌ها از Firebase می‌تونی با این قالب خیلی ساده کار کنی. حتی اگه تجربه زیادی نداری، اینجا کارها برات راحت‌تر شده. البته این قابلیت نیاز به تنظیمات بشتری داره.

### 🔒 ذخیره امن داده (FlutterSecureStorage)
برای ذخیره‌سازی امن داده‌ها (مثل توکن‌ها یا اطلاعات حساس کاربر) می‌تونی از FlutterSecureStorage استفاده کنی. امنیت اطلاعاتت تضمینه.

### 🍴 پشتیبانی از Flavor
اگه پروژه‌ات چندین محیط مختلف (مثل dev، staging، prod) داره، این قالب پشتیبانی از flavor رو هم فراهم می‌کنه تا مدیریت این محیط‌ها خیلی ساده‌تر بشه.

### 🌐 ارتباط با سرور با Dio
مدیریت درخواست‌های HTTP با کتابخونه قدرتمند و حرفه‌ای Dio انجام می‌شه. سریع، راحت و قابل اطمینان.


---
# خیلی راحته اصلا نگران نباش.😊
---

## مراحل نصب و استفاده

### 1. اضافه کردن قالب به پروژه
فایل `mason.yaml` را در ریشه پروژه ایجاد کنید و کد زیر را در آن قرار دهید:
```yaml
bricks:
  feature:
    git:
      url: https://github.com/basicFlutter/mason_bloc_and_clean_bricks.git
      path: bricks/feature
```
### 2 . نصب Mason CLI
ابزار Mason CLI را با دستور زیر نصب و فعال کنید:
```bash

dart pub global activate mason_cli

```
### 3. دانلود قالب‌ها
برای دانلود قالب‌ها دستور
```bash
mason get
```

### 4. ایجاد فایل های مورد نیاز (از این دستور فقط یک بار استفاده شود)
برای ایجاد فایل‌های موردنیاز کل پروژه، از دستور زیر استفاده کنید:

```bash
mason make base
```
### 5. تولید فیچر جدید
برای ایجاد فایل‌های موردنیاز یک فیچر جدید، از دستور زیر استفاده کنید:
```bash
mason make feature --name=نام_فیچر --useCase=نام_مورد_استفاده
```
### مثال
برای ایجاد فیچری به نام user_selector با مورد استفاده‌ای به نام get_users، دستور زیر را اجرا کنید:
```bash
mason make feature --name=user_selector --useCase=get_users
```
### 6. چند زبانه 
برای تعریف متغیرهای چندزبانه در پروژه Flutter، باید فایل‌های موجود در پوشه lib/l10n را ویرایش کنید. در این پوشه، فایل‌های .arb برای هر زبان قرار دارند که ترجمه‌ها را ذخیره می‌کنند. به عنوان مثال، فایل intl_en.arb برای زبان انگلیسی و intl_fa.arb برای زبان فارسی استفاده می‌شود.

#### استفاده از ترجمه‌ها در کد:
بعد از تولید فایل‌های محلی‌سازی با اجرای دستور flutter pub get، می‌توانید به راحتی از متغیرهای تعریف‌شده برای نمایش ترجمه‌ها استفاده کنید. کافیست دستور زیر را در کد خود به‌کار ببرید:
```dart
AppLocalizations localizations = AppLocalizations.of(context)!;
```
### مثال 
```dart
Text(localizations.hello);
```

برای اضافه کردن تنظیمات فایل‌های ترجمه به فایل pubspec.yaml، می‌توانید از ساختار زیر استفاده کنید. این تنظیمات مشخص می‌کند که Flutter باید فایل‌های ترجمه را پردازش کند و کلاس‌های محلی‌سازی را تولید کند:

```yaml

dependencies:
  flutter:
    sdk: flutter
  flutter_localizations:
    sdk: flutter
  intl: ^0.19.0

flutter:
  generate: true

  assets:
    - lib/l10n/intl_en.arb
    - lib/l10n/intl_fa.arb
```

## تنظیم Flavor برای اندروید 

برای تنظیم Flavor، این کدها رو به فایل `build.gradle` در پوشه `app` اضافه کنید:

```gradle
android {
    flavorDimensions "default"

    productFlavors {
        dev {
            dimension  "default"
            applicationIdSuffix ".dev"
        }

        prod {
            dimension  "default"
            applicationIdSuffix ""
        }

        local {
            dimension  "default"
            applicationIdSuffix ".local"
        }
    }
}
```

### اجرای پروژه برای هر Flavor

برای اجرای پروژه در محیط‌های مختلف، از این دستورات استفاده کنید:

- **محیط توسعه (dev):**

  ```bash
  flutter run --flavor dev --target lib/main_dev.dart
  ```

- **محیط تولید (prod):**

  ```bash
  flutter run --flavor prod --target lib/main_prod.dart
  ```

- **محیط محلی (local):**

  ```bash
  flutter run --flavor local --target lib/main_local.dart
  ```
### 7. فایل کامل pubspec.yaml
همچنین باید آخرین ورژن پکیج های مورد نیاز را نیز نصب کنید.

```yaml
name: test_mason
description: "A new Flutter project."

publish_to: 'none' # Remove this line if you wish to publish to pub.dev
version: 1.0.0+1

environment:
  sdk: ^3.6.1

# Dependencies specify other packages that your package needs in order to work.
# To automatically upgrade your package dependencies to the latest versions
# consider running `flutter pub upgrade --major-versions`. Alternatively,
# dependencies can be manually updated by changing the version numbers below to
# the latest version available on pub.dev. To see which dependencies have newer
# versions available, run `flutter pub outdated`.
dependencies:
  flutter:
    sdk: flutter
  flutter_localizations:
    sdk: flutter
  intl: ^0.19.0
  cupertino_icons: ^1.0.8
  flutter_bloc: ^9.0.0
  dio: ^5.3.3
  pretty_dio_logger: ^1.3.1
  firebase_messaging: ^15.1.1
  firebase_core: ^3.4.1
  firebase_crashlytics: ^4.1.1
  awesome_notifications: ^0.10.0
  logger: ^2.0.2+1
  encrypt_shared_preferences: ^0.8.0
  flutter_screenutil: ^5.9.0
  dartz: ^0.10.1
  page_transition: ^2.1.0
  equatable: ^2.0.5
  get_it: ^8.0.1
  gap: ^3.0.1
  persian_datetime_picker: ^3.1.0
  shamsi_date: ^1.0.4
  package_info_plus: ^8.0.2
  flutter_secure_storage: ^9.2.4


dev_dependencies:
  flutter_test:
    sdk: flutter
  build_runner: ^2.4.14

  # The "flutter_lints" package below contains a set of recommended lints to
  # encourage good coding practices. The lint set provided by the package is
  # activated in the `analysis_options.yaml` file located at the root of your
  # package. See that file for information about deactivating specific lint
  # rules and activating additional ones.
  flutter_lints: ^5.0.0

# For information on the generic Dart part of this file, see the
# following page: https://dart.dev/tools/pub/pubspec

# The following section is specific to Flutter packages.
flutter:

  # The following line ensures that the Material Icons font is
  # included with your application, so that you can use the icons in
  # the material Icons class.
  uses-material-design: true
  generate: true
  # To add assets to your application, add an assets section, like this:
  # assets:
  #   - images/a_dot_burr.jpeg
  #   - images/a_dot_ham.jpeg

  # An image asset can refer to one or more resolution-specific "variants", see
  # https://flutter.dev/to/resolution-aware-images

  # For details regarding adding assets from package dependencies, see
  # https://flutter.dev/to/asset-from-package

  # To add custom fonts to your application, add a fonts section here,
  # in this "flutter" section. Each entry in this list should have a
  # "family" key with the font family name, and a "fonts" key with a
  # list giving the asset and other descriptors for the font. For
  # example:
  # fonts:
  #   - family: Schyler
  #     fonts:
  #       - asset: fonts/Schyler-Regular.ttf
  #       - asset: fonts/Schyler-Italic.ttf
  #         style: italic
  #   - family: Trajan Pro
  #     fonts:
  #       - asset: fonts/TrajanPro.ttf
  #       - asset: fonts/TrajanPro_Bold.ttf
  #         weight: 700
  #
  # For details regarding fonts from package dependencies,
  # see https://flutter.dev/to/font-from-package
  assets:
    - lib/l10n/intl_en.arb
    - lib/l10n/intl_fa.arb
```
### آپدیت پکیج ها 
برا نصب آخرین ورژن پکیج ها بعد از اضافه کردن به فایل yaml با دستور زیر به اخرین ورژن ها ارتقا داده میشوند.
```yaml
flutter pub upgrade --major-versions
```








