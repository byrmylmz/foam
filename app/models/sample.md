  >Using fillable is good when you have 2–10 fields, but what if you have 20–50 fields in your model? <br>
  I have experienced creating a table with 56 fields to be exact, and just 3 out of those fields are needed to be protected. <br>
  Trust me, it’s quite of a work. “I’m not saying that it’s not good” using fillable in this situation, you may, but if you want an easier way to secure it from mass-assignment, then guarded will be more preferable.

```php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Category extends Model
{
    use HasFactory;
    protected $guarded = [];
}
```
[Click for sample github repo](https://github.com/byrmylmz/booksql-laravel/blob/97d66e894aa4255ae2ccbf005260b25f65d1419c/app/Models/Category.php#L11)