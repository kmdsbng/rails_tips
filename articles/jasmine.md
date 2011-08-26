# -*- encoding: utf-8 -*-
jasmine
======

概要
------

JavaScript用ユニットテストツールです。

インストール
-----

Gemfileに以下の行を追加

    gem 'jasmine'

使用例
-----

    describe("Jasmine", function() {
      it("makes testing JavaScript awesome!", function() {
        expect(yourCode).toBeLotsBetter();
      });
    });



ネスト

    describe('some suite', function () {

      var suiteWideFoo;

      beforeEach(function () {
        suiteWideFoo = 0;
      });

      describe('some nested suite', function() {
        var nestedSuiteBar;
        beforeEach(function() {
          nestedSuiteBar=1;
        });

        it('nested expectation', function () {
          expect(suiteWideFoo).toEqual(0);
          expect(nestedSuiteBar).toEqual(1);
        });

      });

      it('top-level describe', function () {
        expect(suiteWideFoo).toEqual(0);
        expect(nestedSuiteBar).toEqual(undefined); // Spec will fail with ReferenceError: nestedSuiteBar is not defined
      });
    });

Spyの仕組みを使ってモックテストもできます。



サイト
-----
[github pivotal / jasmine](https://github.com/pivotal/jasmine/)



更新日
-----
2011/08/25 23:53:08
