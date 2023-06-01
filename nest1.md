### nest入门


#### 创建 nest
```
npm install -g @nestjs/cli
nest new 项目名
npm update -g @nestjs/cli
```
#### nest 命令
```
nest -h

```
![image](https://github.com/jumpingFinger/weblog/assets/36480878/f7c4497d-a59c-4448-9356-c68063a3ca5b)


#### generate

```
nest generate module test
nest generate controller test
nest generate service  test

nest generate application // 生成所有目录，没有git init 和 装包操作
```
[schematics模版定义](https://github.com/nestjs/schematics/tree/master/src/lib)
![image](https://github.com/jumpingFinger/weblog/assets/36480878/8386606e-121a-48ee-b794-26ac562f4769)

### nest项目

#### tsconfig

"strictNullChecks": true 选项会启用严格的 null 检查，TypeScript 编译器会在变量声明时检查是否有可能为 null 或 undefined 的情况，并强制程序员在使用这些变量之前进行检查或处理。

"noImplicitAny": true 选项会禁止隐式的 any 类型，要求所有的变量、函数参数、返回值都要显式地声明类型。

"strictBindCallApply": true 选项会启用严格的 this 检查，TypeScript 编译器会检查函数的 this 绑定是否正确，并要求程序员在使用函数时明确指定 this 的类型。

"forceConsistentCasingInFileNames": true 选项会强制要求文件名的大小写规范一致，防止由于大小写不一致导致的编译错误。

"noFallthroughCasesInSwitch": true 选项会禁止在 switch 语句中出现 case 穿透现象，即当一个 case 分支执行后没有 break 或 return 语句时，TypeScript 编译器会报错。

通过设置这些编译选项，可以使 TypeScript 编译器更加严格地检查代码，保证代码的质量和可靠性。

"module": "commonjs" 选项指定了模块的输出类型，这里设置为 commonjs，表示采用 CommonJS 规范输出模块。

"declaration": true 选项会生成相应的 .d.ts 文件，用于提供给 TypeScript 模块外的代码使用。

"removeComments": true 选项会移除编译后的 JavaScript 代码中的注释，减小文件大小。

"emitDecoratorMetadata": true 选项会在装饰器中为类添加元数据，用于反射和编译时的类型检查。

"experimentalDecorators": true 选项会启用实验性的装饰器特性，用于扩展类和方法的功能。

"allowSyntheticDefaultImports": true 选项允许从没有默认导出的模块中导入模块的默认导出。

"target": "es2017" 选项指定了 TypeScript 编译的目标 JavaScript 版本，这里设置为 ES2017。

"sourceMap": true 选项会生成相应的 .js.map 文件，用于调试 TypeScript 代码。

"outDir": "./dist" 选项指定了编译后的 JavaScript 文件的输出目录。

"baseUrl": "./" 选项指定了相对路径的基准路径。

"incremental": true 选项会开启 TypeScript 的增量编译功能，可以提高编译的速度。

"skipLibCheck": true 选项会跳过编译 TypeScript 的内置库文件，以提高编译速度。

通过设置这些编译选项，可以根据具体项目的需要来调整 TypeScript 编译器的行为，以提高代码的可靠性和性能。





