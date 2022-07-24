# Frontend Mentor - Profile card component solution

This is a solution to the [Profile card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/profile-card-component-cfArpWshJ).

The card contains basic user information, a photo and statistics. Two of its sections look like jigsaw puzzle pieces fitted together, and the page background has two circles translated halfway off of the viewport horizontally and vertically.

## Links

- [Solution on Frontend Mentor]()
- [Live Site on GitHub Pages]()

## Screenshot

![web page with a turquoise background showing a card with a user picture, name, age, city, and their amount of followers, likes and photos.](./screenshot.jpeg)

## My process

### What I learned

In this project, I have explored **absolute positioning** of elements. The design presented an interesting challenge: the card's top section (with the turquoise pattern) and middle section (with the user image and personal information) must look like two puzzle pieces fitted together. To achieve that, the user image is absolutely positioned, centered and then translated vertically by 50%. This, along with the white `box-shadow` around it (which is the same color as the middle section), creates the appearance that the middle section has a tab and the top section has a blank, just like two jigsaw puzzle pieces.

```css
.user-card__img {
  display: block;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 50%;
  box-shadow: 0 0 0 0.35rem white;
}
```

Working on this project also showed the importance of **cross-browser compatibility**. Initially, the white ring around the user image was made using the `outline` property. However, after finding out that `outline` does not respect `border-radius` in Safari, it had to be changed to `box-shadow` to ensure the same experience in that browser. [This seems to be a bug in WebKit](https://bugs.webkit.org/show_bug.cgi?id=20807).

| ![profile card with round user photo and a white square outline around it instead of a white ring](./screenshot-safari-square-outline.jpeg) |
| :-----------------------------------------------------------------------------------------------------------------------------------------: |
|                                          **`outline` does not respect `border-radius` in Safari.**                                          |

The two circles in the page's background are also absolutely positioned. To follow the design, they had to be translated 50% off of the viewport horizontally and vertically, which caused **side-scrolling**. To fix that, both images were placed in a container with the size of the viewport and `overflow: hidden`.

This project also allowed me to practice the use of **semantic HTML5 markup**, **Flexbox**, **CSS relative units**, **CSS custom properties**, the **BEM naming convention**, **utility classes** and the use of **Git** and **GitHub**.

### Continued development

In future projects, I want to keep exploring **cross-browser compatibility**, especially in **mobile devices**. This project has a footer at the very bottom of the page that could be partially hidden in devices with non-rectangular screens. This might be a good use case for the `safe-area-inset-*` environment variables, which I want to learn more about.

### Useful resources

- [_Bug 20807 - outline doesn't respect border-radius for styles other than auto_ — WebKit Bugzilla](https://bugs.webkit.org/show_bug.cgi?id=20807) - This bug report helped me understand why the outline around the user image was rendered as a square in iOS Safari.
- [_Outline on rounded image renders as square on Safari._](https://github.com/tailwindlabs/tailwindcss/discussions/7649) - This discussion on the GitHub repository of Tailwind CSS gave me the idea of using `box-shadow` instead of `outline` for the ring around the user image.
- [_env()_ — MDN Web Docs](https://www.example.com) - Page about the `env()` CSS function, which I want to explore in future projects.

## Author

- Frontend Mentor - [@JulioCinquina](https://www.frontendmentor.io/profile/JulioCinquina)
