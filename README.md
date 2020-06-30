# backpackr-homework

## 1. Card

사용방법
1. npm package
  https://www.npmjs.com/package/1.card 에서 packgae를 다운로드 하는 경우에는 추가 모듈 설치없이 바로 사용할 수 있다.
  
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
   git에서 해당 소스를 클론한 후 사용할 모듈을 프로젝트로 옮긴 후에 사용할 수 있다. 단 이때는 아래의 package가 package.json에 추가 되어 있어야 한다.

   ```json
     "devDependencies": {
       "@babel/cli": "^7.8.4",
       "@babel/core": "^7.8.3",
       "@babel/plugin-transform-runtime": "^7.8.3",
       "@babel/preset-env": "^7.8.3"
     },
     "dependencies": {
       "@babel/runtime": "^7.8.4"
     }
   ```

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
  https://www.npmjs.com/package/2.input 에서 packgae를 다운로드 하는 경우에는 추가 모듈 설치없이 바로 사용할 수 있다.
  
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
   git에서 해당 소스를 클론한 후 사용할 모듈을 프로젝트로 옮긴 후에 사용할 수 있다. 단 이때는 아래의 package가 package.json에 추가 되어 있어야 한다.

   ```json
     "devDependencies": {
       "@babel/cli": "^7.8.4",
       "@babel/core": "^7.8.3",
       "@babel/plugin-transform-runtime": "^7.8.3",
       "@babel/preset-env": "^7.8.3"
     },
     "dependencies": {
       "@babel/runtime": "^7.8.4"
     }
   ```

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

