# beatvis
Open song tagging format for music visualizers

## Format Specification 

Files use json and are named as `{name}.beat.json` or `{name}.vis.json` (TODO)

TypeScript draft 1

```ts
type Manifest = {
  v: 0; // Format version
  meta: Metadata;
}

type Metadata = {
  author: string // file author
  song: SongMetadata
}

// TODO
type SongMetadata = {
  title: string
}

// string for english
// object for foreign languages
type Text = string | {
  original: string;
  // if original has non-latin letters
  romanized?: string;
  // optional english translation
  translation?: string;
}

/*
example Text = {
  original: "化けの花",
  romanized: "Bake no Hana",
  translation: "Flower of Transformation",
}
*/



type Singer = {
  id: string
  fullName?: Text
  name: Text
  color?: string
}

type LyricTag = {
  type: "lyric"
  parts: LyricPart[]
}

type LyricPart = {
  singers: string[]
  text: Text
}

// wait hold on we cant map syllables like this hm
```
