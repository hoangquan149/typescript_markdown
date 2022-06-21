# Typescript

## Ưu điểm của Typescript

-  Dễ dàng phát triển dự án lớn
-  Hỗ trợ OPP mạnh
-  Tổ chức code dỡ dàng hơn
-  Hỗ trợ các tính năng mới nhất của `Javascript`

## Các kiểu dữ liệu hay sử dụng

-  Any - Một biến được khai báo có kiểu dữ liệu này có thể là một giá trị string, number hoặc bất kỳ kiểu dữ liệu nào
-  Number
   -  Chỉ có giá trị là số nguyên `number` hoặc số thực `float`
-  String
   -  Chỉ có giá trị là `string`, bao quang với dấu 'nháy đơn' hoặc "nháy kép"
-  Boolean
   -  Chỉ có giá trị `true` hoặc `false`
-  Array
   -  Chỉ có giá trị là 1 array
-  Void
   -  Sử dụng với hàm khi không trả về giá trị nào

## Function

-  ### Function trong typescript có thể khai báo như sau
   -  Function là từ khóa
   -  nameFunc : tên hàm
   -  Trong ngoặc là các tham số có kiểu như là : number, string ...
   -  `: string {}` là kiều trả về của hàm
   -  Nếu để kiểu trả là `string` mà không là `string` sẽ bị lỗi

```
   function nameFunc (a: number, b: number): string {
      do some thing
      return a + b;
   }

   <!-- Arrow Function -->
   const myFunc = (a; number): number => {
      return a
   }

```

-  ### Optional and Default Parameter

   -  Optional: Có thể bỏ qua các tham số bằng cách thêm dấu `?` vào sau tham số mà mình muốn optional

```
   <!-- VD: Optional -->
   function nameFunc (name?:string, age: number): string{
      return `name: ${name} age: ${age}`
   }

   works
   nameFunc(18)
```

-  ### Default Parameter
   -  Default Parameter: Có thể set luôn giá trị tham số, khi gọi hàm có thể truyền hoặc không

```
   <!-- VD: Default Parameter -->
  function nameFunc (name:string = 'John', age: number): string{
      return `name: ${name} age: ${age}`
   }

   works
   nameFunc(14)

```

## Hướng đối tượng

-  ## Class
   -  Class là 1 bản thiết kế ra đối tượng , có thể tạo ra nhiều đối tượng từ bản thiết kế đó.

VD :

```
class Student{
   <!-- Thuộc tính -->
   name: string;
   age: age:

   <!-- Phương thức để tạo đối tượng -->

   constructor(name: string,age: number){
      this.name = name;
      this.age = age;
   }

   <!-- Các Phương thức -->
   getStudent(): string {
      return `Học sinh: ${this.name} Tuổi: ${this.age}`
   }

   lean(){

   }

}

<!-- Khời tạo đối tượng -->
const student1 = new Student('John', 18)

console.log(student1)

{
   name: 'John',
   age: 18
}

```

-  ## Tính đóng gói
   -  Phạm vi truy cập trong class: private, protected, public mặc định sẽ là public
      -  Private : Chỉ ở trong phạm vi class mới truy cập được
      -  Public : Phạm vi nào cũng có thể truy cập được
      -  Protected : Chỉ có class con kế thừa mới có thể truy cập được

VD :

```
class Student{
   <!-- Thuộc tính khai báo với private -->
   private name: string;
   private age: age:

   <!-- Phương thức để tạo đối tượng -->

   constructor(name: string,age: number){
      this.name = name;
      this.age = age;
   }

   <!-- Các Phương thức -->
   getStudent(): string {
      return `Học sinh: ${this.name} Tuổi: ${this.age}`
   }

   lean(){

   }

}

<!-- Khời tạo đối tượng -->
const student1 = new Student('John', 18)

console.log(student1)

{
   name: 'John',
   age: 18
}

```

-  ## Tính kế thừa
   -  Class con kế thừa lại tất cả phương thức và thuộc tính của class cha

VD:

```
   class Father{
      name: string;
      money: number;

      constructor(name: string, money: number){
         this.name = name;
         this.money = money;
      }

      //
      showInfo(): string{
         return `${this.name} ${this.money}`;
      }
   }

   }

   <!-- Con sẽ kế thừa lại hết tất cả các thuộc tính và phương thức của cha -->
   class Children extents Father{
      laptop: string;
      constructor(name: string, money: number,laptop: string){
         super(name,money)
         this.laptop = laptop

      }

      showInfo():string{
         return `${this.laptop} ${this.name} ${this.money}`;
     }


   }

```

-  ## interface

   -  `interface` là một kiểu dữ liệu có thể tạo ra các đối tượng, các đối tượng được tạo ra phải thi hành các field và method của nó

-  `interface` có optional properties và method

VD:

```
   <!-- Sử dụng optional properties -->

   interface Student {
      name: string;
      age: number;
      address?: string;

   }
```

-  Thuộc tính `readonly` là chỉ được đọc nếu sửa sẽ báo lỗi

VD:

```
   <!-- Sử dụng thuộc tính readonly -->

   interface Person {
      name: string;
      readonly age: number;
   }

   const person1: Person = {
      name: 'John',
      age: 18
   }

   person1.age = 19 <!-- error -->

```

-  `interface` cũng có kế thừa như `class`

VD:

```
   interface Contact {
      email: string;
      phone: string;
   }

   interface Person extends Contact{
      name:string;
      age: number;
   }

   const person1 : Person = {
      email: "person1@gmail.com",
      phone: '0122',
      name: "person",
      age: 18
   }
```

## Generics

-  Là một kiểu cho phép viết function, class, interface có thể tái sử dụng và nhiều kiểu khác nhau.

VD:

```
interface Student{
   id: number,
   name: string
}

const numberList: Array<number> = [1,2,3,4,5];
const wordList: Array<string> = ['easy','frontend'];


const listStudent: Array<Student> = [
   {id: 1, name: 'John1'},
   {id: 2 name: 'John2'}

]

```

# Utility Types

-  ### Pick<T,K>
   -  Sử dụng `Pick` để lấy ra cái key cần thiết

VD:

```
interface Todo {
  title: string;
  description: string;
  completed: boolean;
}

type TodoPreview = Pick<Todo, "title" | "completed">;

const todo: TodoPreview = {
  title: "Clean room",
  completed: false,
};

```

-  ### Partial
   -  Sử dụng `Partial` để lấy ra các key mình muốn, nó sẽ biến tất cả các field giống optionnal

VD:

```
interface Todo {
  title: string;
  description: string;
  completed: boolean;
}

const todo: Todo = {
  title: "Clean room",
};

```

-  ### Required
   -  Nếu tất cả các field của `interface` của bạn là `optional properties` nó sẽ biến tất cả các field thành required

VD:

```
   interface Todo{
      title?: string;
      description?: string;
      completed?: boolean;
   }

   <!-- error -->
   const newTodo: Required<Todo> = {
      title: 'Hello',
   }

   <!-- work -->
   const newTodo: Required<Todo> = {
      title: 'Hello',
      description: 'đâs',
      completed: true,
   }

```

-  ### ReadOnly
   -  Sử dụng `ReadOnly` chỉ được đọc giá trị không được set lại giá trị

VD:

```
   interface Todo{
      title: string;
      description: string;
   }

   const newTodo: ReadOnly<Todo> = {
      title: 'Hello',
      description: 'description'
   }

   <!-- error -->
   newTodo.title = 'Hello1'


```

-  ### Omit<T,K>
   -  Sử dụng `Omit` Lấy tất cả field ngoại trừ field

VD:

```
   interface Todo{
      title: string;
      description: string;
   }

   const newTodo: Omit<Todo, 'title'> = {
      description: 'description'
   }


```
