# Blocks

## Platform differences

#### lineHeight

```ts
type PixelLineHeight = string;
type RelativeLineHeight = number;
/* Web */
type LineHeight = RelativeLineHeight | PixelLineHeight;
/* iOS & Android */
type LineHeight = PixelLineHeight;
```

```ts
type LineHeight = PixelLineHeight;
```

#### borderStyle

```ts
/**
 * Web
 *
 * @required for border to appear
 *
 * @default "none"
 */
type BorderStyle =
  | "none"
  | "hidden"
  | "dotted"
  | "dashed"
  | "solid"
  | "double"
  | "groove"
  | "ridge";

/**
 * iOS & Android
 *
 * @optional
 *
 * @default "solid"
 */
type BorderStyle = "solid" | "dotted" | "dashed";
```

```ts
/**
 * blocks
 *
 * @optional
 *
 * @default "solid"
 */
type BorderStyle = "solid" | "dotted" | "dashed";
```

#### boxSizing

```ts
/**
 * Web
 *
 * @optional
 *
 * @default "content-box"
 */
type BoxSizing = "content-box" | "border-box";

/**
 * iOS & Android
 *
 * @default "border-box"
 */
type BoxSizing = "border-box";
```

```ts
/**
 * blocks
 *
 * @default "border-box"
 */
type BoxSizing = "border-box";
```

#### shadow

```ts
/**
 * Web
 *
 * @optional
 *
 * @default "none"
 */
interface Shadow {
  inset?: boolean;
  offsetX: PixelValue;
  offsetY: PixelValue;
  blurRadius: PixelValue;
  spreadRadius: PixelValue;
  color: Color;
}

/**
 * iOS
 *
 * @optional
 *
 * @default undefined
 */

interface ShadowOffset {
  width: number; // x
  height: number; // y
}

interface Shadow {
  shadowColor: Color;
  shadowOffset: ShadowOffset;
  shadowOpacity: number;
  shadowRadius: number;
}

/**
 * Android
 *
 * @optional
 *
 * @default undefined
 */

interface Shadow {
  elevation: number;
}
```

```ts
/**
 * blocks
 *
 * @optional
 *
 * @default undefined
 */
interface Shadow {
  color: Color;
  offset: {
    x: number;
    y: number;
  };
  opacity: number;
  radius: number;
}
```

#### fontFamily

```ts
/**
 * Web, iOS, Android & blocks
 *
 * @optional
 *
 * @default OS/Device Specific
 *
 * String specified is unique per platform hence it's inclusion.
 */
type FontFamily = string;
```

#### CSS Values

#### display

```ts
/**
 * Web
 *
 * @optional
 *
 * @default element specific
 */

type Display = "block" | "grid" | "flex" | "inline" | "table" ...

/**
 * iOS & Android
 *
 * @optional
 *
 * @default "flex"
 */

type Display = "flex"
```

```ts
/**
 * blocks
 *
 * @optional
 *
 * @default "flex"
 */

type Display = "flex";
```

#### Rendering Text

On Web you're able to render text anywhere in the DOM, on iOS & Android you can only render text inside a `<Text />` component. Blocks adheres to this convention, meaning that any text must be wrapped in a `<Text />` component.

#### Outline / Border

Border is supported on Web, iOS and Android. Outline is only supported on Web. Therefore blocks only supports border at this present time.
