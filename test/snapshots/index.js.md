# Snapshot report for `test/index.js`

The actual snapshot is saved in `index.js.snap`.

Generated by [AVA](https://ava.li).

## generates source maps

> Snapshot 1

    `export default (() => <div>␊
        <p>test</p>␊
        <p>woot</p>␊
        <style jsx>{`p { color: red }␊
    /*# sourceMappingURL=data:application/json;charset=utf-8;base64,eyJ2ZXJzaW9uIjozLCJzb3VyY2VzIjpbInNvdXJjZS1tYXBzLmpzIl0sIm5hbWVzIjpbXSwibWFwcGluZ3MiOiJBQUlnQixBQUNjLFVBQUMiLCJmaWxlIjoic291cmNlLW1hcHMuanMiLCJzb3VyY2VzQ29udGVudCI6WyJleHBvcnQgZGVmYXVsdCAoKSA9PiAoXG4gIDxkaXY+XG4gICAgPHA+dGVzdDwvcD5cbiAgICA8cD53b290PC9wPlxuICAgIDxzdHlsZSBqc3g+eydwIHsgY29sb3I6IHJlZCB9J308L3N0eWxlPlxuICA8L2Rpdj5cbilcbiJdfQ== */␊
    /*@ sourceURL=source-maps.js */`}</style>␊
      </div>);`

## handles dynamic `this` value inside of arrow function

> Snapshot 1

    `import React, { Component } from 'react';␊
    export default class Index extends Component {␊
      static getInitialProps() {␊
        return {␊
          color: 'aquamarine'␊
        };␊
      }␊
    ␊
      render() {␊
        var _this = this;␊
    ␊
        return <div>␊
            {[1, 2].map(function (idx) {␊
            return <div key={idx}>␊
                {[3, 4].map(function (idx2) {␊
                return <div key={idx2}>{_this.props.color}</div>;␊
              })}␊
              </div>;␊
          })}␊
            {[1, 2].map(function (idx) {␊
            return <div key={idx}>␊
                <div>␊
                  {_this.props.color}␊
                  <div className="something">␊
                    <React.Fragment>␊
                      <div>␊
                        <div>{_this.props.color} hello there</div>␊
                      </div>␊
                    </React.Fragment>␊
                  </div>␊
                </div>␊
              </div>;␊
          })}␊
            <style jsx>{`␊
              div {␊
                background: ${this.props.color};␊
              }␊
            `}</style>␊
          </div>;␊
      }␊
    ␊
    }`

## ignores when attribute is absent

> Snapshot 1

    `const a = () => <div>␊
        <p>hi</p>␊
        <style>{'woot'}</style>␊
      </div>;`

## ignores whitespace around expression container

> Snapshot 1

    `export default (() => <div>␊
        <p>test</p>␊
        <p>woot</p>␊
        <p>woot</p>␊
        <style jsx>{`p { color: red }`}</style>␊
      </div>);`

## should have different jsx ids

> Snapshot 1

    `const color = 'red';␊
    const otherColor = 'green';␊
    ␊
    const A = () => <div>␊
        <p>test</p>␊
        <style jsx>{`␊
          p {␊
            color: ${color};␊
          }␊
        `}</style>␊
      </div>;␊
    ␊
    const B = () => <div>␊
        <p>test</p>␊
        <style jsx>{`␊
          p {␊
            color: ${otherColor};␊
          }␊
        `}</style>␊
      </div>;␊
    ␊
    export default (() => <div>␊
        <A />␊
        <B />␊
      </div>);`

## should not add the data-jsx attribute to components instances

> Snapshot 1

    `const Test = () => <div>␊
        <span>test</span>␊
        <Component />␊
        <style jsx>{`␊
          span {␊
            color: red;␊
          }␊
        `}</style>␊
      </div>;`

## works with class

> Snapshot 1

    `export default class {␊
      render() {␊
        return <div>␊
            <p>test</p>␊
            <style jsx>{`␊
              p {␊
                color: red;␊
              }␊
            `}</style>␊
          </div>;␊
      }␊
    ␊
    }`

## works with css tagged template literals in the same file

> Snapshot 1

    `import css from 'styled-jsx/css';␊
    export default (({␊
      children␊
    }) => <div>␊
        <p>{children}</p>␊
        <style jsx>{styles}</style>␊
      </div>);␊
    const styles = css`␊
      p {␊
        color: red;␊
      }␊
    `;␊
    ␊
    class Test extends React.Component {␊
      render() {␊
        return <div>␊
            <p>{this.props.children}</p>␊
            <style jsx>{styles}</style>␊
          </div>;␊
      }␊
    ␊
    }`

## works with dynamic element

> Snapshot 1

    `export default (({␊
      level = 1␊
    }) => {␊
      const Element = `h${level}`;␊
      return <Element className="root">␊
          <p>dynamic element</p>␊
          <style jsx>{`␊
            .root {␊
              background: red;␊
            }␊
          `}</style>␊
        </Element>;␊
    });␊
    export const TestLowerCase = ({␊
      level = 1␊
    }) => {␊
      const element = `h${level}`;␊
      return <element className="root">␊
          <p>dynamic element</p>␊
          <style jsx>{`␊
            .root {␊
              background: red;␊
            }␊
          `}</style>␊
        </element>;␊
    };␊
    const Element2 = 'div';␊
    export const Test2 = () => {␊
      return <Element2 className="root">␊
          <p>dynamic element</p>␊
          <style jsx>{`␊
            .root {␊
              background: red;␊
            }␊
          `}</style>␊
        </Element2>;␊
    };`

## works with dynamic element in class

> Snapshot 1

    `export default class {␊
      render() {␊
        const Element = 'div';␊
        return <Element className="root">␊
            <p>dynamic element</p>␊
            <style jsx>{`␊
              .root {␊
                background: red;␊
              }␊
            `}</style>␊
          </Element>;␊
      }␊
    ␊
    }␊
    const Element2 = 'div';␊
    export const Test2 = class {␊
      render() {␊
        return <Element2 className="root">␊
            <p>dynamic element</p>␊
            <style jsx>{`␊
              .root {␊
                background: red;␊
              }␊
            `}</style>␊
          </Element2>;␊
      }␊
    ␊
    };`

## works with existing identifier for _JSXStyle

> Snapshot 1

    `export const _JSXStyle = '_JSXStyle-literal';␊
    export default function () {␊
      return <div>␊
          <p>test</p>␊
          <style jsx>{`␊
            p {␊
              color: red;␊
            }␊
          `}</style>␊
        </div>;␊
    }`

## works with exported jsx-style (CommonJS modules)

> Snapshot 1

    `"use strict";␊
    ␊
    module.exports = () => <p><style jsx>{`p { color:red; }`}</style></p>;`

## works with exported non-jsx style (CommonJS modules)

> Snapshot 1

    `"use strict";␊
    ␊
    module.exports = () => <p><style>{`p { color:red; }`}</style></p>;`

## works with expressions in template literals

> Snapshot 1

    `const darken = c => c;␊
    ␊
    const color = 'red';␊
    const otherColor = 'green';␊
    const mediumScreen = '680px';␊
    const animationDuration = '200ms';␊
    const animationName = 'my-cool-animation';␊
    const obj = {␊
      display: 'block'␊
    };␊
    export default (({␊
      display␊
    }) => <div>␊
        <p>test</p>␊
        <style jsx>{`␊
          p.${color} {␊
            color: ${otherColor};␊
            display: ${obj.display};␊
          }␊
        `}</style>␊
        <style jsx>{`p { color: red }`}</style>␊
        <style jsx global>{`␊
          body {␊
            background: ${color};␊
          }␊
        `}</style>␊
        <style jsx global>{`␊
          body {␊
            background: ${color};␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          p {␊
            color: ${color};␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          p {␊
            color: ${color};␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          p {␊
            color: ${darken(color)};␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          p {␊
            color: ${darken(color) + 2};␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          @media (min-width: ${mediumScreen}) {␊
            p {␊
              color: green;␊
            }␊
            p {␊
              color: ${`red`};␊
            }␊
          }␊
          p {␊
            color: red;␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          p {␊
            animation-duration: ${animationDuration};␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          p {␊
            animation: ${animationDuration} forwards ${animationName};␊
          }␊
          div {␊
            background: ${color};␊
          }␊
        `}</style>␊
    ␊
        <style jsx>{`␊
          span {␊
            display: ${display ? 'block' : 'none'};␊
          }␊
        `}</style>␊
        <style jsx>{`␊
          span:before {␊
            display: ${display ? 'block' : 'none'};␊
            content: '\\`';␊
          }␊
        `}</style>␊
      </div>);`

## works with fragment

> Snapshot 1

    `import React from 'react';␊
    export default (() => <>␊
        <p>Testing!!!</p>␊
        <p className="foo">Bar</p>␊
        <>␊
          <h3 id="head">Title...</h3>␊
          <React.Fragment>␊
            <p>hello</p>␊
            <>␊
              <p>foo</p>␊
              <p>bar</p>␊
            </>␊
            <p>world</p>␊
          </React.Fragment>␊
        </>␊
        <style jsx>{`␊
          p {␊
            color: cyan;␊
          }␊
          .foo {␊
            font-size: 18px;␊
            color: hotpink;␊
          }␊
          #head {␊
            text-decoration: underline;␊
          }␊
        `}</style>␊
      </>);␊
    ␊
    function Component1() {␊
      return <>␊
          <div>test</div>␊
        </>;␊
    }␊
    ␊
    function Component2() {␊
      return <div>␊
          <style jsx>{`␊
            div {␊
              color: red;␊
            }␊
          `}</style>␊
        </div>;␊
    }`

## works with global styles

> Snapshot 1

    `const Test = () => <div>␊
        <style jsx global>{`␊
          body {␊
            color: red;␊
          }␊
    ␊
          :hover {␊
            color: red;␊
            display: flex;␊
            animation: foo 1s ease-out;␊
          }␊
    ␊
          div a {␊
            display: none;␊
          }␊
    ␊
          [data-test] > div {␊
            color: red;␊
          }␊
        `}</style>␊
      </div>;␊
    ␊
    const Test2 = () => <style global jsx>{`p { color: red }`}</style>;`

## works with multiple jsx blocks

> Snapshot 1

    `const attrs = {␊
      id: 'test'␊
    };␊
    ␊
    const Test1 = () => <div>␊
        <span {...attrs} data-test="test">␊
          test␊
        </span>␊
        <Component />␊
        <style jsx>{`␊
          span {␊
            color: red;␊
          }␊
        `}</style>␊
      </div>;␊
    ␊
    const Test2 = () => <span>test</span>;␊
    ␊
    const Test3 = () => <div>␊
        <span>test</span>␊
        <style jsx>{`␊
          span {␊
            color: red;␊
          }␊
        `}</style>␊
      </div>;␊
    ␊
    export default class {␊
      render() {␊
        return <div>␊
            <p>test</p>␊
            <style jsx>{`␊
              p {␊
                color: red;␊
              }␊
            `}</style>␊
          </div>;␊
      }␊
    ␊
    }`

## works with non styled-jsx styles

> Snapshot 1

    `export default (() => <div>␊
        <p>woot</p>␊
        <style dangerouslySetInnerHTML={{␊
        __html: `body { margin: 0; }`␊
      }} />␊
        <style jsx>{`p { color: red }`}</style>␊
      </div>);`

## works with stateless

> Snapshot 1

    `export default (() => <div>␊
        <p>test</p>␊
        <p>woot</p>␊
        <p>woot</p>␊
        <style jsx>{`p { color: red }`}</style>␊
      </div>);`
