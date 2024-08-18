
**A callback is a function passed as an argument to another function. This technique allows a function to call another function. A callback function can run after another function has finished**


**Example:** Extracting Images Using Puppeteer
```
// Extract Images

  const images = await page.$$eval("img", (elements) =>

    elements.map((element) => ({

      src: element.src,

      slt: element.alt,

    }))

  );
```

