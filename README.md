# Code snippet

![Tested React Version](https://img.shields.io/badge/React-v18.1.0-blue.svg)
![Tested framer-motion Version](https://img.shields.io/badge/framer--motion-v%5E6.3.3-%23ff69b4.svg)

## React custom hook (Element start and end position for scroll)

- #### Usages
  > Used with framer-motion to create scroll animation that use the scroll as it's playback mechanism
- #### Requirements

  - [React](https://www.npmjs.com/package/react)
  - [TypeScript](https://create-react-app.dev/docs/adding-typescript/)
  - [Framer-motion](https://www.npmjs.com/package/framer-motion)

- #### Example

```js
// import useViewportScroll to get the current scroll position
import {motion, useViewportScroll, useTransform} from 'framer-motion';
// import the custom hook
import { useRefScrollProgress } from "../hooks/scrollStartEnd";

const ExampleElement:React.FC = () =>{
    const {scrollYProgress} = useViewportScroll();
    // this returns the distance where the element referenced starts and end
    const [targetRef, start end] = useScrollProgress();

    const opacityFadeIn_animation = useTransform(scrollYProgress,[start,end], [0, 1]);

    return(
        // reference the element
        <motion.div ref={targetRef}
            style={{
                opacity: opacityFadeIn_animation
            }}
        >
            <p>The div will only start fading-in when the user scroll reaches the div's
            position and continue or reverse the animation based on the scroll distance</p>
        
        </motion.div>
    )

}

```
