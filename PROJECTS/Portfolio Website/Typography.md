
### **Typography (.tsx)**

```Typescript
'use client';

import { TypographyProps } from "@/types/Typography";

import "./Typography.scss"

  

const Typography = ({ variant, children, ...props }:TypographyProps) => {

    return (

      <div {...props} className={`${variant}`}>

        {children}

      </div>

    );

  };

  export default Typography;
```


### Typography (.scss)

```scss

.h1 {

    font-size: 3.812rem;

    font-weight: bold;

    line-height: 1.2;

    font-family: 'Avenir Black';

  }

  .h2 {

    font-size: 3.062rem;

    font-weight: bold;

    line-height: 1.3;

    font-family: 'Avenir Black';

  

  }

  .h3 {

    font-size: 2.438rem;

    font-weight: bold;

    line-height: 1.4;

    font-family: 'Avenir Black';

  

  }

  .h4 {

    font-size: 1.938rem;

    font-weight: bold;

    line-height: 1.5;

    font-family: 'Avenir Black';

  

  }

  .h5 {

    font-size: 1.562rem;

    font-weight: bold;

    line-height: 1.6;

    font-family: 'Avenir Black';

  

  }

  

  .body {

    font-size: 1.250rem;

    font-weight: 400;

    line-height: 1.6;

    font-family: 'Avenir Heavy';

  }

  .title1 {

    font-size: 1rem;

    font-weight: 600;

    line-height: 1.4;

    font-family: 'Avenir Medium';

  }

  

  .title2 {

    font-size: 0.812rem;

    font-weight: 600;

    line-height: 1.4;

    font-family: 'Avenir Medium';

  }

  

  .caption {

    font-size: 0.625rem;

    font-weight: 400;

    line-height: 1.6;

    font-family: 'Avenir Roman';

  }
```


### Typography(.stroies.ts)

``` Typescript
import type {Meta, StoryObj } from '@storybook/react'

import Typography from './Typography'

  
  

const meta = {

    title: 'Atoms/Typography',

    component: Typography,

    parametrs:{

        controls: {expanded:true}

    },

    tags: ['autodocs'],

    argsTypes:{

        variant: {

            control: 'select',

            options: ['caption', 'h1', 'h2', 'h3', 'h4', 'h5', 'h6', 'title1', 'title2', 'body'],

          },

    }

} as Meta<typeof Typography>;

  

export default meta;

  

type Story = StoryObj<typeof meta>;

  

export const Default: Story = {

    args: {

        variant: 'body',

        children: 'Test Caption'

    }

}
```