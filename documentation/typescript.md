
## Typescript


### [Adjacent overload signatures](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/adjacent-overload-signatures.md)

> Require that member overloads be consecutive (adjacent-overload-signatures from TSLint)


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
interface IFoo {
	foo(s: string): void;
	foo(n: number): void;
	bar(): void;
	foo(sn: string | number): void;
}
*/
// Good
interface IFoo {
	foo(sn: string | number): void;
	foo(s: string): void;
	foo(n: number): void;
	bar(): void;
}

```
<br />



### [Array type](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/array-type.md)

> Requires using either T[] or Array<T> for arrays (array-type)


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(async () => {
	type A = Array<string>;
})();
*/
// Good
(async () => {
	type A = string[];
})();

```
<br />



### [Ban ts ignore](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/ban-ts-ignore.md)

> Bans “// @ts-ignore” comments from being used (ban-ts-ignore)


:white_check_mark: Enabled (error)

```javascript

// Bad

/*
(() => {
	if (false) {
		// @ts-ignore
		console.log('hello');
	}
})();
*/

```
<br />



### [Ban types](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/ban-types.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	const a: String = 'a';
	const b: Number = 1;
})();
*/
// Good
(() => {
	const a: string = 'a';
	const b: number = 1;
})();

```
<br />



### [Camelcase](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/camelcase.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
import { no_camelcased } from 'eslint';

(() => {
	no_camelcased();
	const my_favorite_color = '#112C85';
	console.log(my_favorite_color);
})();
*/
// Good
import { no_camelcased as noCamelcased } from 'eslint';

(() => {
	noCamelcased();
	const myFavoriteColor = '#112C85';
	console.log(myFavoriteColor);
})();

```
<br />



### [Class name casing](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/class-name-casing.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
class invalidClassName {}
class Another_Invalid_Class_Name {}
const bar = class invalidName {};
interface someInterface {}
*/
// Good
class ValidClassName {}
class AnotherValidClassName {}
const bar = class ValidName {};
interface ISomeInterface {
	name: string;
}

```
<br />



### [Consistent type assertions](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/consistent-type-assertions.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/* 
(() => {
	type Foo2 = object;
	const foo = <Foo2>{};
	const x = { text: true } as Foo2;
})();
*/

// Good
(() => {
	type T = object;
	type Foo = object;
	const data = { test: true };
	const x: T = { ...data };
	const y = { ...data } as any;
	const z = { ...data } as unknown;
	function foo(some: T) { throw { bar: 5 } as Foo; }
	foo({ ...data } as T);
})();

```
<br />



### [Explicit function return type](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/explicit-function-return-type.md)

> 


:x: Disabled

```javascript

// Good
// Should indicate that no value is returned (void)
function test() {
	return;
}

// Should indicate that a number is returned
const fn = function () {
	return 1;
};

// Should indicate that a string is returned
const arrowFn = () => 'test';

class Test {
	// Should indicate that no value is returned (void)
	public method() {
		return;
	}
}

```
<br />



### [Explicit member accessibility](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/explicit-member-accessibility.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
class Animal {
	constructor(name) {
		this.animalName = name;
	}
	animalName: string;
	get name(): string {
		return this.animalName;
	}
	set name(value: string) {
		this.animalName = value;
	}
	walk() {
		// method
	}
}
*/
// Good
class Animal {
	private _animalName: string;
	public constructor(name: string) {
		this._animalName = name;
	}
	public get name(): string {
		return this._animalName;
	}
	public set name(value: string) {
		this._animalName = value;
	}
	public walk() {
		// method
	}
}

```
<br />



### [Generic type naming](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/generic-type-naming.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	type ReadOnly<SomeType extends object> = {
		readonly [TKey in keyof SomeType]: SomeType[TKey]
	};
})();
*/
// Good
(() => {
	type IReadOnly<TSomeType extends object> = {
		readonly [TKey in keyof TSomeType]: TSomeType[TKey]
	};
})();

```
<br />



### [Indent](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/indent.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
type ReadOnly<SomeType extends object> = {
	readonly [TKey in keyof SomeType]: SomeType[TKey]
};
*/
// Good
type ReadOnly<TSomeType extends object> = {
	readonly [TKey in keyof TSomeType]: TSomeType[TKey]
};

```
<br />



### [Interface name prefix](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/interface-name-prefix.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
interface Animal {
	name: string;
}
*/
// Good
interface IAnimal {
	name: string;
}

```
<br />



### [Member delimiter style](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/member-delimiter-style.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
interface IFoo {
	name: string,
	greet(): void,
}
*/
// Good
interface IFoo {
	name: string;
	greet(): void;
}

```
<br />



### [Member naming](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/member-naming.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
class HappyClass {
	private foo: string;
	private bar = 123;
	public _fizz() {}
}
*/
// Good
class HappyClass {
	private _foo: string;
	private _bar = 123;
	public fizz() {}
}

```
<br />



### [Member ordering](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/member-ordering.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
class Foo {
	private _c: string; // -> field
	protected static e: string; // -> field
	public d: string; // -> field

	public static a(): void {} // -> method
	public b(): void {} // -> method

	public constructor() {
		console.log('constructor');
	} // -> constructor
}
*/
// Good
class Foo {
	protected static e: string; // -> field
	public d: string; // -> field
	private _c: string; // -> field

	public constructor() {
		console.log('constructor');
	} // -> constructor

	public static a(): void {} // -> method
	public b(): void {} // -> method
}

```
<br />



### [No array constructor](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-array-constructor.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(async () => {
	const arr1 = Array<number>(0, 1, 2);
	const arr2 = new Array<number>(0, 1, 2);

	const arr1 = Array(0, 1, 2);
	const arr2 = new Array(0, 1, 2);
})();
*/

// Good
(async () => {
	const arr3 = Array(500);
	const arr4 = new Array(3);
})();

```
<br />



### [No empty interface](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-empty-interface.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(async () => {
	// an empty interface
	interface IFoo {}

	// an interface with only one supertype (Bar === Foo)
	interface IBar extends IFoo {}

	// an interface with an empty list of supertypes
	interface IBaz {}
})();
*/
// Good
(async () => {
	interface IFoo {
		name: string;
	}
	interface IBar extends IFoo {
		email: string;
	}
	interface IBaz {
		name: string;
	}
})();

```
<br />



### [No explicit any](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-explicit-any.md)

> 


:x: Disabled

```javascript

// Bad

/*
const age: any = 'seventeen';
*/
// Good
// not that good but okay in this configuration
const age: any = 'seventeen';

```
<br />



### [No extraneous class](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-extraneous-class.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
class ConstructorOnly {
	public constructor() {
		console.log('constructor');
	}
}
*/
// Good
class ConstructorOnly {
	private _version: string = '1.1.0'
	public constructor() {
		console.log(`constructor ${this._version}`);
	}
}

```
<br />



### [No for in array](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-for-in-array.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
for (const x in [3, 4, 5]) {
	console.log(x);
}
*/
// Good
// still not okay because not allowed by this rules: no-restricted-syntax, guard-for-in
for (const x in { a: 3, b: 4, c: 5 }) {
	console.log(x);
}

```
<br />



### [No inferrable types](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-inferrable-types.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(async () => {
	const foo: number = 5;
	const bar: boolean = true;
	const baz: string = 'str';
})();
*/
// Good
(async () => {
	const foo = 5;
	const bar = true;
	const baz = 'str';
})();

```
<br />



### [No misused new](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-misused-new.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(async () => {
	class C {
		new(): C;
	}

	interface IFoo {
		new (): IFoo;
		constructor(): void;
	}
})();
*/
// Good
(async () => {
	class C {
		public constructor() {}
	}
	interface IFoo {
		new (): C;
	}
})();

```
<br />



### [No namespace](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-namespace.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
module foo {}
namespace foo {}
declare module foo {}
declare namespace foo {}
*/
// Good
declare module 'foo' {}

```
<br />



### [No non null assertion](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-non-null-assertion.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	interface IFoo {
		bar?: string;
	}

	const foo: IFoo = { bar: 'bar' };
	const includesBaz: boolean = foo.bar!.includes('baz');
})();
*/
// Good
(() => {
	interface IFoo {
		bar?: string;
	}

	const foo: IFoo = { bar: 'baz' };
	const includesBaz: boolean = (foo.bar || '').includes('baz');
})();

```
<br />



### [No parameter properties](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-parameter-properties.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	class Foo {
		constructor(readonly name: string) {}
	}
	class Foo {
		constructor(private name: string) {}
	}
	class Foo {
		constructor(protected name: string) {}
	}
	class Foo {
		constructor(public name: string) {}
	}
})();
*/
// Good
(() => {
	class Foo {
		constructor(name: string) {}
	}
})();

```
<br />



### [No require imports](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-require-imports.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
const eslint = require('eslint');
*/
// Good
import eslint from 'eslint';

```
<br />



### [No this alias](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-this-alias.md)

> 


:x: Disabled

```javascript

// Bad
/*
(() => {
	const self = this;

	setTimeout(() => {
		self.doWork();
	});
})();
*/
// Good
(() => {
	// already covered by consistent-this
	const _this = this;

	setTimeout(() => {
		_this.doWork();
	});
})();

```
<br />



### [No type alias](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-type-alias.md)

> 


:x: Disabled

```javascript

// Good
(() => {
	// primitives
	type Foo = 'a' | 'b';

	type Foo2 = string;

	type Foo3 = string[];

	// reference types
	interface IBar {}
	class Baz implements IBar {}

	type Foo5 = IBar & Baz;
})();

```
<br />



### [No unnecessary qualifier](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-unnecessary-qualifier.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
namespace A {
	export type B = number;
	const x: A.B = 3;
}
*/
// Good
namespace X {
	export type B = number;
}
namespace Y {
	export const x: X.B = 3;
}

```
<br />



### [No unnecessary type assertion](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-unnecessary-type-assertion.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	function foo(x: number): number {
		return x!; // unnecessary non-null
	}
})();
*/
// Good
(() => {
	function foo(x: number | undefined): number {
		return x!;
	}
})();

```
<br />



### [No unused vars](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-unused-vars.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
// Write-only variables are not considered as used.
let y = 10;
y = 5;

// A read for a modification of itself is not considered as used.
let z = 0;
z = z + 1;
*/
// Good
// Write-only variables are not considered as used.
let y = 10;
y = 5;

// A read for a modification of itself is not considered as used.
let z = 0;
z = z + y;

console.log(z);

```
<br />



### [No use before define](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-use-before-define.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	alert(a);
	const a = 10;
})();
*/
// Good
(() => {
	const a = 10;
	alert(a);
})();

```
<br />



### [No useless constructor](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-useless-constructor.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	class A {
		constructor() {}
	}
})();
*/
// Good
(() => {
	class A {
		public constructor() {
			this._doSomething();
		}
		private _doSomething() {
			document.write('something');
		}
	}
})();

```
<br />



### [No var requires](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/no-var-requires.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	var foo1 = require('foo');
	const foo2 = require('foo');
	let foo3 = require('foo');
})();
*/
// Good
import eslint from 'eslint';

```
<br />



### [Prefer function type](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/prefer-function-type.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	interface IFoo {
		(): string;
	}

	function foo(bar: { (): number }): number {
		return bar();
	}

	interface IFoo2 extends Function {
		(): void;
	}
})();
*/
// Good
(() => {
	interface IFoo {
		bar: number;
		(): void;
	}

	function foo(bar: { baz: number;(): string }): string {
		return bar();
	}

	interface IFoo2 {
		bar: string;
	}
	interface IBar extends IFoo2 {
		(): void;
	}
})();

```
<br />



### [Prefer interface](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/prefer-interface.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	type Test = { x: number };
})();
*/
// Good
(() => {
	interface ITest {
		x: number;
	}
})();

```
<br />



### [Promise function async](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/promise-function-async.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	const arrowFunctionReturnsPromise = () => Promise.resolve('value');

	function functionReturnsPromise() {
		return Math.random() > 0.5 ? Promise.resolve('value') : false;
	}
})();
*/
// Good
(() => {
	const arrowFunctionReturnsPromise = async () => 'value';

	async function functionReturnsPromise() {
		return Math.random() > 0.5 ? 'value' : false;
	}
})();

```
<br />



### [Restrict plus operands](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/restrict-plus-operands.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	const foo = '5.5' + 5;
})();
*/
// Good
(() => {
	const foo = parseInt('5.5', 10) + 10;
})();

```
<br />



### [Triple slash reference](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/triple-slash-reference.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Good
(() => {
	/// <reference path="../../../../node_modules/@types/react/index.d.ts" />
})();

```
<br />



### [Type annotation spacing](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/type-annotation-spacing.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	const foo:string = 'bar';
})();
*/
// Good
(() => {
	const foo: string = 'bar';
})();

```
<br />



### [Unified signatures](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/unified-signatures.md)

> 


:white_check_mark: Enabled (error)

```javascript

// Bad
/*
(() => {
	interface IFoo {
		foo(sn: string | number): void;
		foo(s: string): void;
		foo(n: number): void;
		bar(): void;
	}
})();
*/
// Good
(() => {
	interface IFoo {
		foo(sn: string | number): void;
		bar(): void;
	}
})();

```
<br />


