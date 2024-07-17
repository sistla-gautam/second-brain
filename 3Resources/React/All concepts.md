- separation of concerns
    
    - states that logic that performs different actions should be separated into different components
    - fetching the data should not be combined with displaying the data
    - components mainly divided into 2 components
        - container component
        - presentational component
- container components
    
    - provide, create or hold data
    - does not contains any type of UI on its own
    - contains presentataional components as its children
- presentational components
    
    - primary job is to present the data on the UI
    - take data from the parent container components
    - does not alter the data
    - does not alter state, unless required for UI change
- svg as a component in react
    
    - if we use create-react-app v2 or above, we can import svg as a component into our react app
        
        - importing the svg
        
        ```jsx
        import { ReactComponent as YourSvg } from './your-svg.svg';
        ```
        
        - using the component in the code
        
        ```jsx
        const App = () => (
         <div>
           <YourSvg />
         </div>
        );
        ```
        
- svg manipulation libraries
    
    [https://www.smashingmagazine.com/2014/11/styling-and-animating-svgs-with-css/](https://www.smashingmagazine.com/2014/11/styling-and-animating-svgs-with-css/)
    
    - bonsaijs (no documentation, still in construction)
        
    - vivusjs
        
        [https://maxwellito.github.io/vivus/](https://maxwellito.github.io/vivus/)
        
        - simple svg manipulation
        - no dependencies
        - only does path animations
    - svgjs
        
        [https://svgjs.dev/docs/3.0/](https://svgjs.dev/docs/3.0/)
        
        - most versatile of all
        - no dependencies
        - has a simple syntax
        - comprehensive documentation
    - gsap
        
        gsap is for animation, not specifically for svgs
        
        can be used, but will be a quite difficult
        
    - snapsvg
        
        [http://snapsvg.io/docs/](http://snapsvg.io/docs/)
        
        - simple to use
        - works on multiple browsers
        - more faster than other libraries
    - lazy line painter
        
    - paperjs
        
        - not simple
        - requires additional download and setup
        - not straightforward documentation
        - but, more diverse features than svgjs and snapsvg
- svg manipulation with external css
    
    [https://jenkov.com/tutorials/svg/svg-and-css.html](https://jenkov.com/tutorials/svg/svg-and-css.html)
    
    [https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/SVG_and_CSS](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/SVG_and_CSS)
    
    [https://stackoverflow.com/questions/18434094/how-to-style-svg-with-external-css?answertab=scoredesc#tab-top](https://stackoverflow.com/questions/18434094/how-to-style-svg-with-external-css?answertab=scoredesc#tab-top)
    
    - can be manipulated only when the svg code is use as an inline code inside the HTML document
        
    - if not, we can edit the values using the styles tag inside the svg element
        
        ```jsx
        <style type="text/css" >
              <![CDATA[
        
                circle {
                   stroke: #006600;
                   fill:   #00cc00;
                }
        
              ]]>
            </style>
        ```
        
- removing js from svg
    
    [](https://stackoverflow.com/questions/3689455/disable-javascript-in-iframe-div#:~:text=HTML5%20introduces%20the%20sandbox%20attribute,disables%20JavaScript%20loading%20and%20execution)[https://stackoverflow.com/questions/3689455/disable-javascript-in-iframe-div#:~:text=HTML5](https://stackoverflow.com/questions/3689455/disable-javascript-in-iframe-div#:~:text=HTML5) introduces the sandbox attribute,disables JavaScript loading and execution.
    
    - removing js from svg, so as to prevent unwanted scripts from running by the SVG
    - placing the svg in a img tag
        - will work, but does not suit our requirements
        - the svg will at the end still contain the script tags that contain codes
        - our svg needs to be displayed via the SVGMT library
    - replacing the script tags from the svg themselves using a regex approach
        - will remove the script tags, but needs to be parsed twice
            
            - once by the regex to search for script tags
            - once so we can use it for the SVGMT tags
            
            ```jsx
                        var pattern = new RegExp("<script.*</script>", "gs");
                        var replacedContent = content.replaceAll(pattern, "");
            ```
            
- hooks
    
    - useState
        
        - used to manage state of particular data or properties
        
        ```jsx
        const [state, setState] = useState(<initialValue>);
        ```
        
        _**state**_ is the variable name
        
        _**setState**_ is the function used to set the state
        
        - reading the value of the state
            
            done by just reading the value of state like a variable
            
        - updating the value of the state
            
            done by passing the updated value as a function parameter to the setState function
            
    - useEffect
        
        - allows you to perform side effects on your component (fetching data, updating variables, etc)
        - accepts one argument, one optional argument
        
        ```jsx
        useEffect(<function>, <dependencyList>)
        ```
        
        the function is the run under the following conditions
        
        - no dependency - runs every render (similar to onTick from unreal)
        - empty dependency list - runs only on the first render
        - non zero dependency list - runs on the first render and every time there is a change in one of the dependency(s)
        - effect cleanup
            - this is done to cleanup the effect function, so it does not keep running in the background and take up resources or reduce the performance
            - done by providing a return statement to the function
    - useRef
        
        serves 2 purposes
        
        - to store the reference of a DOM element
            
            ```jsx
            const varName = useRef(<initialValue>);
            ```
            
        - to store the value of data that should not cause a re-render
            
            ```jsx
            const inputElement = useRef();
            
            ```