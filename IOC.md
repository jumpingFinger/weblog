###  IOC（Inverse Of Control）

在 class 上声明依赖了啥，然后让工具去分析我声明的依赖关系，根据先后顺序自动把对象创建好了

有一个放对象的容器，程序初始化的时候会扫描 class 上声明的依赖关系，然后把这些 class 都给 new 一个实例放到容器里。

创建对象的时候，还会把它们依赖的对象注入进去。完成了自动的对象创建和组装

种依赖注入的方式叫做 Dependency Injection

从主动创建依赖到被动等待依赖注入，这就是 Inverse Of Control，反转控制



### 调试nest

调试node

```
node --inspect-brk index.js
```

### 调试
```Json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "启动程序",
      "skipFiles": ["<node_internals>/**"],
      "stopOnEntry": true,
      "program": "${workspaceFolder}/src/index.js",
      "outFiles": ["${workspaceFolder}/**/*.js"]
    }
  ]
}
```
stopOnEntry 是在首行断住，和 --inspect-brk 一样的效果


### Providers
···typeScirpt
import { Module } from '@nestjs/common';
import { AppController } from './app.controller';
import { AppService } from './app.service';

@Module({
  imports: [],
  controllers: [AppController],
  providers: [
    AppService,
    {
      provide: 'person',
      useValue: {
        age: 10,
        name: '无忧',
      },
    },
    {
      provide: 'personFactory',
      useFactory() {
        return {
          age: 20,
          name: '无忧',
        };
      },
    },
    {
      provide: 'personDynamic',
      useFactory(person: { name: string }, appServer: AppService) {
        return {
          name: person.name,
          desc: appServer.getHello(),
        };
      },
      inject: ['person', AppService],
    },

    {
      provide: 'asyncPersonDynamic',
      useExisting: 'asyncPersonDynamicExist',
      async useFactory() {
        await new Promise((resolve, reject) => {
          setTimeout(resolve, 1000);
        });

        return {
          name: '无忧',
          desc: '异步',
        };
      },
    },
  ],
})
export class AppModule {}
···