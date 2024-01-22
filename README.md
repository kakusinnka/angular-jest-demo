# AngularJestDemo
[Angular unit testing with Jest](https://medium.com/@megha.d.parmar2018/angular-unit-testing-with-jest-2023-2676faa2e564)

## 步骤 1：使用以下命令创建新项目：
```
ng new angular-jest-demo
```

## 第 2 步：使用以下命令卸载所有 karma jasmin 包：
```
npm uninstall karma karma-chrome-launcher karma-coverage karma-jasmine karma-jasmine-html-reporter @types/jasmine jasmine-core
```

## 步骤 3：从angular.json文件中删除测试对象

## 第 4 步：安装下面提到的软件包：
```
npm i -save-dev jest @types/jest jest-preset-angular
```

## 第 5 步：在根文件夹中创建setup-jest.ts文件
```
import 'jest-preset-angular/setup-jest';
```