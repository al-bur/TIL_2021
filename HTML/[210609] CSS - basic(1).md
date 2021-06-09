## [210609] CSS - basic(1)

### 1. CSS 선택자

- `,` - 쉼표를 사용하면 나열한 모든 클래스, id, 태그에 css를 적용 시킬 수 있다.





### 2. nth child

---

- `태그,class,id등 :nth-child()` -> 해당 요소들 밑에 존재하는 자식들중 몇 번째 자식에게 css를 적용시킬 것인지를 지정해줄 수 있다.

  - ex) category-kinds라는 클래스 하위에 홀수번째로 존재하는 자식 요소들에게만 `border-right`를 주고 싶을 때

  ```css
  .category-kinds > :nth-child(odd) {
       border-right: 0.02rem solid gray;
     }
  ```

   

