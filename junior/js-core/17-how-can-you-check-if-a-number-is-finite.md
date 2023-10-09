### Як перевірити, чи число є скінченним?
1. isFinite()
2. Number.isFinite() (ES6)
3. Порівняти число з `-Infinity` i `+Infinity`.
4. Порівняти число з `Number.MAX_VALUE` і `Number.MIN_VALUE`

> Різниця між isFinite() і Number.isFinite() у тому що Number.isFinite() не проводить приведення типів. на відміну від  isFinite(), якщо передати у Number.isFinite() не числове значення то він ніколи не поверне true.