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
npm i --save-dev jest @types/jest jest-preset-angular
```

## 第 5 步：在根文件夹中创建setup-jest.ts文件
```
import 'jest-preset-angular/setup-jest';
```

## 步骤6：要创建jest.config文件，请使用以下命令：
```
npx jest --init
```
![](/src/assets/images/step005.png)

## 我们需要为 TypeScript 配置文件安装 ts-node
```
npm i ts-node
```

## Step 7 ： 更新tsconfig.spec.json文件
```
/* To learn more about this file see: https://angular.io/config/tsconfig. */
{
  "extends": "./tsconfig.json",
  "compilerOptions": {
    "outDir": "./out-tsc/spec",
    "types": [
      "jest" // 1
    ],
    "esModuleInterop": true, // 2
    "emitDecoratorMetadata": true // 3
  },
  "include": [
    "src/**/*.spec.ts",
    "src/**/*.d.ts"
  ]
}
```

## 第 8 步：在 script 标签内package.json添加 jest 配置
```
    "test": "jest --verbose",
    "test:coverage": "jest --coverage",
    "test:watch": "jest --watch"
```

## 步骤 9：编写单元测试用例
```
import { ComponentFixture, TestBed } from '@angular/core/testing';
import { AppComponent } from './app.component';

describe('AppComponent', () => {
  let component: AppComponent;
  let fixture: ComponentFixture<AppComponent>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [AppComponent],
    }).compileComponents();
  });

  beforeEach(() => {
    fixture = TestBed.createComponent(AppComponent);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });

  it('should create the app', () => {
    expect(component).toBeTruthy();
  });

  it(`should have as title 'demo-angular-jest'`, () => {
    expect(component.title).toEqual('demo-angular-jest');
  });

  it('should render the title', () => {
    const compiled = fixture.nativeElement as HTMLElement;
    expect(compiled.querySelector('.content span')?.textContent).toContain('demo-angular-jest app is running!');
  });
});
```

## 进行测试
```
npm run test:coverage
```