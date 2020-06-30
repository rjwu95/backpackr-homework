# backpackr-homework

이 package는 Vue로 작성되어 있으므로 Vue 프로젝트에서 사용할 수 있다.
아래의 두가지 모듈은 모두 다음과 같은 선행조건이 있어야 한다.

vue cli를 사용하여 프로젝트를 생성한 경우 바로 사용할 수 있고, 이를 수동으로 설정한다면 아래와 같다.(version 4.x)
```javascript
.babelrc
{
  presets: [
    '@vue/cli-plugin-babel/preset'
  ]
}
또는 babel.config.js
module.exports = {
  presets: [
    '@vue/cli-plugin-babel/preset'
  ]
}

npm i core-js vue
npm i -D @vue/cli-plugin-babel @vue/cli-service vue-template-compiler
```

## 1. Card

사용방법
}

1. npm package
  https://www.npmjs.com/package/1.card 에서 packgae를 다운로드 하여 사용할 수 있다.
  
  ```javascript
  import { ResponsiveCard, HorizontalCard, VerticalCard } from '1.card'
  
  export default {
  	name: 'Sample',
    components: { ResponsiveCard, HorizontalCard, VerticalCard }
  }
  또는
  import card from '1.card'
  
  export default {
  	name: 'Sample',
    components: {
      ResponsiveCard: card.ResponsiveCard, 			
      HorizontalCard: card.HorizontalCard, 	
      VerticalCard: card.VerticalCard
    }
  }
  ```
  
2. Github Source clone
   git에서 해당 소스를 클론한 후 사용할 모듈을 프로젝트로 옮긴 후에 사용할 수 있다.

   ```javascript
   import { ResponsiveCard, HorizontalCard, VerticalCard } from './1.card'
   
   export default {
    name: 'Sample',
    components: { ResponsiveCard, HorizontalCard, VerticalCard }
   }
   또는
   import card from './1.card'
   
   export default {
   	name: 'Sample',
    components: {
      ResponsiveCard: card.ResponsiveCard, 			
      HorizontalCard: card.HorizontalCard, 	
      VerticalCard: card.VerticalCard
    }
   }
   ```

   


### ResponsiveCard
| props   |   type   |  default |
|---------|:--------:|------:|
| image |  string | 'https://www.spartacapital.com/wp-content/uploads/2019/04/Sample-Logo-square.png' |
| label |    string   |   'Card Label' |
| title | string |    'Card Title' |
| hilight | string |    'Hilight' |
| crossOut | string |    'Cross Out' |
| rating | number |    3 |
| description | string |    'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?' |
| horizontalTitle | string |    'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?' |
| verticalWidth | string |    '300px' |
| horizontalWidth | string |    '800px' |
| horizontalHeight | string |    '250px' |
| writer | string |    'John Doe' |
| heightOfChangeDirectionPoint | string | '440px' |
| heightOfVisibleRatingBoxPoint | string | '480px' |
| heightOfVisibleDescriptionPoint | string | '530px' |

### HorizontalCard
| props   |   type   |  default |
|---------|:--------:|------:|
| image |  string | 'https://www.spartacapital.com/wp-content/uploads/2019/04/Sample-Logo-square.png' |
| title | string |    'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?' |
| rating | number |    3 |
| description | string |    'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?' |
| writer | string |    'John Doe' |
| height | string |    '250px' |
| width | string |    '800px' |

### VerticalCard
| props   |   type   |  default |
|---------|:--------:|------:|
| image |  string | 'https://www.spartacapital.com/wp-content/uploads/2019/04/Sample-Logo-square.png' |
| label |    string   |   'Card Label' |
| title | string |    'Card Title' |
| hilight | string |    'Hilight' |
| crossOut | string |    'Cross Out' |
| rating | number |    3 |
| description | string |    'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?' |
| width | string | '300px' |

## 2. Input

사용방법
1. npm package
  https://www.npmjs.com/package/2.input 에서 packgae를 다운로드 하여 사용할 수 있다.
  
  ```javascript
  import { Input, DisabledInput, ReadonlyInput } from '2.input'
  
  export default {
  	name: 'Sample',
    components: { Input, DisabledInput, ReadonlyInput }
  }
  또는
  import input from '2.input'
  
  export default {
  	name: 'Sample',
    components: {
      Input: input.Input, 			
      DisabledInput: input.DisabledInput, 	
      ReadonlyInput: input.ReadonlyInput
    }
  }
  ```
  
2. Github Source clone
   git에서 해당 소스를 클론한 후 사용할 모듈을 프로젝트로 옮긴 후에 사용할 수 있다.
   
   ```javascript
   import { Input, DisabledInput, ReadonlyInput } from './2.input'
   
   export default {
   	name: 'Sample',
     components: { Input, DisabledInput, ReadonlyInput }
   }
   또는
   import input from './2.input'
   
   export default {
   	name: 'Sample',
     components: {
       Input: input.Input, 			
       DisabledInput: input.DisabledInput, 	
       ReadonlyInput: input.ReadonlyInput
     }
   }
   ```


### Input
| props   |   type   |  default |
|---------|:--------:|------:|
| defaultContent |  string | '' |
| maxlength |    number   |   500 |
| disabled | boolean |    false |
| readonly | boolean |    false |
| placeholder | string |    '내용을 입력해 주세요.' |

| event   |
|---------|
| save |

### DisabledInput
| props   |   type   |  default |
|---------|:--------:|------:|
| defaultContent |  string | '' |
| maxlength |    number   |   500 |
| disabled | boolean |    true |
| readonly | boolean |    false |
| placeholder | string |    '내용을 입력해 주세요.' |

| event   |
|---------|
| save |

### ReadonlyInput
| props   |   type   |  default |
|---------|:--------:|------:|
| defaultContent |  string | '' |
| maxlength |    number   |   500 |
| disabled | boolean |    false |
| readonly | boolean |    true |
| placeholder | string |    '내용을 입력해 주세요.' |

| event   |
|---------|
| save |

