# Code Conventions
## Source code format
ODA source code is developed on various platforms and editors. Therefore common formatting should be used:
- Use four spaces for indentation. Tabs must not be used.
- Use UNIX newlines `\n`.
- Prefer US-ASCII characters in source code. Non-ascii characters should be encoded, e.g., ä -> \u00e4.
- Use UTF-8 in code comments and other information intended for other developers.

### Eclipse settings
- UTF-8
  * (Project) > Properties > Resources > "Text file encoding: Other: UTF-8"
- Spaces
  * Window > Preferences > General > Editors > Text Editors > "Displayed tab width:4"; "Insert spaces for tabs:check"
  * Window > Preferences > Java > Code Style > Formatter > Indentation > tab policy : Spaces only
- Allow * in imports
  * Window > Preferences > Java > Code Style > Organize Imports > "Number of imports needed for .* = 2"; "Number of static imports needed for .* =2"
- Keep source formatting to edited lines only
  * Window > Preferences > Java > Editor > Save Actions > Format source code: check "Format edited lines"
- Encoding Non-ascii characters:
  * AnyEdit Tools plugin: Convert > To Unicode Notation.

## Java
- If methods need to return empty values use `Optional` instead of nulls.
- Return empty collections instead of nulls.
- Use assertions like `this.bar = Objects.requireNonNull(bar);` to set potentially null value. Or `org.springframework.util.Assert.*`
- Do not add unnecessary `if (foo == null)` checks. Trust conventions!
- Use Java 8 streams instead of looping collections.
- Do not add unnecessary comments. Name the method well instead.
- Keep the scope as small as possible.
- Favor RuntimeExceptions instead of Checked exceptions. This removes unnecessary crap.
- Use return Collections.emptyList() instead of return new ArrayList()
- Use return Collections.singletonList(item) instead of new ArrayList().add(item)
- Prefer (immutable) public final attributes instead of Private attributes with getters.
- Unit testing of null value capturing for dto classes is not needed as long as requireNonNull is used. Trust conventions.
- Use ArrayList instead of Vector. Vector is a relic and was not originally defined for collections.
- In Java we use camelCase
- Clean Code: A Handbook of Agile Software Craftsmanship has some great practices (a few should be taken with a grain of salt, though). If you don't have access to the book, have a look at the JS version.

## JUnit
- Use assertThat and hamcrest matchers instead of assertEquals
- Use `@Test(expected = SomeException.class)` instead of try-catch

## Application Interfaces
- In API:s, we use PascalCase.

## Spring Framework
- Use constructor injection instead of setter injection.

## JavaScript
- In JavaScript we use camelCase.
- JavaScript is standardised to and validated towards ES6.
- JSX-content uses double quotes. Single quotes everywhere else. (ESLint rule: jsx-quotes)
- No spaces around objects (ESLint rule: babel/object-curly-spacing)
- https://github.com/ryanmcdermott/clean-code-javascript

## React
- https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb

## Build Tools
- In Java we use `./gradlew clean build`
- In JavaScript `yarn install`
- Others `./build.sh`

## Misc

Master the conventions, but also keep in mind the crucial non-code aspects of software development. While bad code has sometimes contributed to project failures, in most cases the problems have run deeper.

![hint](https://twitter.com/practicingdev/status/811956403745210368)