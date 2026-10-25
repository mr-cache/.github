<div align="center">

# MrCache

### Redis caching, close to your Eloquent queries.

Build with Laravel. Keep cache behavior explicit.

[Get started](https://github.com/mr-cache/mr-cache#readme) · [Explore the code](https://github.com/mr-cache/mr-cache) · [العربية](https://github.com/mr-cache/mr-cache/blob/4.x/README_AR.md) · [Packagist](https://packagist.org/packages/mrcache/mrcache)

</div>

---

MrCache is an open-source Redis query-caching library for Laravel and Eloquent. Add caching to your models, choose a lifetime for each query, and keep a direct database path when you need it.

```php
use Illuminate\Database\Eloquent\Model;
use MrCache\Traits\CacheableModel;

class Post extends Model
{
    use CacheableModel;
}

$posts = Post::where('is_published', true)->withCustomTTL(60)->get();
$fresh = Post::withoutCaching()->find(1);
```

<table>
<tr>
<td width="33%" valign="top">

**Fits Eloquent**

Work with your models and familiar query chains.

</td>
<td width="33%" valign="top">

**Keeps control visible**

Choose query lifetimes and bypass caching explicitly.

</td>
<td width="33%" valign="top">

**Puts correctness first**

Understand invalidation and consistency before relying on cached results.

</td>
</tr>
</table>

### Start building

```sh
composer require mrcache/mrcache
```

Follow the [installation and configuration guide](https://github.com/mr-cache/mr-cache#readme) before enabling caching. Compatibility, supported queries and consistency guarantees depend on the package version—check the [package repository](https://github.com/mr-cache/mr-cache) and [tags](https://github.com/mr-cache/mr-cache/tags) for the version you use.

### Build with us

We welcome reproducible bug reports, regression tests, practical examples, documentation improvements and measured performance work.

[Report a bug or ask a question](https://github.com/mr-cache/mr-cache/issues) · [Explore contributions](https://github.com/mr-cache/mr-cache/pulls) · [Read the license](https://github.com/mr-cache/mr-cache/blob/4.x/LICENSE)

---

### بالعربية

**MrCache مكتبة مفتوحة المصدر لتخزين استعلامات Laravel وEloquent مؤقتاً باستخدام Redis.**

استخدم نماذجك واستعلاماتك المعتادة، وحدّد مدة التخزين لكل استعلام، وتجاوز الكاش عندما تحتاج قراءة مباشرة من قاعدة البيانات. راجع سلوك الإصدار الذي تستخدمه وحدود الإبطال والاتساق قبل التفعيل.

[ابدأ من الدليل العربي](https://github.com/mr-cache/mr-cache/blob/4.x/README_AR.md) · [المستودع الرئيسي](https://github.com/mr-cache/mr-cache) · [الأسئلة والمشكلات](https://github.com/mr-cache/mr-cache/issues)
