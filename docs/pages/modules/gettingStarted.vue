<template>
  <div>
    <doc-section id="getting-started" name="Getting started">
      <div class="bs-callout bs-callout-success">
        <h4>About this project</h4>
        <p>
          The goal of project is provide a easy way to organize, customize, and incorporate all elements of your's project.
          For this we organize all elements into self contained components, splitting all variables and codes put into each folder,
          each component have yours variables, events, styles and more.
          Bootue its group of elements components self contained, organized, with multiple featured to incorporate and using in any SPA project.
        </p>
        <p>
          Bootue make simple way to extends and modify boostrap variables, effects and featured, her provide a possibility
          to you using party of outhers frameworks together with boostrap components,
          create a new one or using only elements that you need.
        </p>
      </div>
      <h3 class="text-center">We organize and structure a new set of boostrap's element, <br/>and create more new elements.
      </h3>
      <div class="bs-callout bs-callout-success">
        <p>
          We raise the web components concept to 100%, all coponents are self contained, yours has its own variables, scss, js and events.
          Bootue provides an easy path to create new components or modify in organized pattern way.
        </p>
      </div>
      <h3 class="text-center">Don't need to import any css, js or fonts, <br/>bootue components its self contained</h3>
      <div class="bs-callout bs-callout-success">
        <p>
          You can choose how components the project will use, or integrate the components inside to project, its easy to customize
          , create or perhaps mixin with another frameworks parts. <router-link to="/extend">See more</router-link>
        </p>
      </div>
      <hr/>

      <div class="panel panel-primary">
        <div class="panel-heading">
          <h5 class="panel-title text-center">Requirements</h5>
        </div>

        <div class="panel-body">
          <ul>
            <li>Vue-Cli - (browserify or webpack)</li>
            <li>Node - Sass (vue-loader-sass)</li>
            <li>Setup webpack to make url-loader for fonts (font-awesome)</li>
          </ul>
        </div>
      </div>
      <hr/>
      <h4>Let`s started</h4>
      <p>First all bootue is build using vue-cli system, you need to install and setup a <a href="https://github.com/vuejs-templates/browserify-simple" target="_blank">vueify (browserify)</a> or <a
        href="https://github.com/vuejs/vue-loader" target="_blank">vue-loader(webpack)</a> env, <a
        href="https://github.com/vuejs/vue-cli" target="_blank">Install Vue Cli</a>, you maybe use webpack or browserfy.</p>

      <doc-code language="bash">
        $ npm install -g vue-cli
        $ vue init webpack-simple demo // bootue works with webpack or browserify
        $ vue init browserify demo
      </doc-code>

      <hr/>

      <b>Webpack env</b>
      <p>Make sure to install sass pre-compiled environment (in all cli installation he ask you if you like to setup sass <code>(default is NO)</code>, write YES, and be happy)</p>
      <img src="dist/imgs/usesass.png" class="img-responsive-center"/>

      <hr/>
      <h4>ES6 - Babel</h4>
      <doc-code language="javascript">
        $ npm install bootue

        import Bootue from 'bootue'
        Vue.use(Bootue) // import all components
      </doc-code>
      or
      <doc-code language="javascript">
        import alert from 'bootue/src/alert'

        Vue.component('alert', alert)

        // or
        new Vue({
          components: {
            alert
          }
        })
      </doc-code>
      or
      <doc-code language="javascript">
        $ npm install bootue

        // >>> or
        var alert = require('bootue/src/alert');
        var alert = require('bootue/src').alert;

        new Vue({
          components: {
            alert: alert
          }
        })


        // After babel 6, yoou need iteract with default property.
        var alert = require('bootue/src/alert').default;
      </doc-code>
      <hr/>
      <h4>Webpack Env - Font Awesome</h4>
      <p>Some components using font-awesome icons (font-awesome is optional), if you like to use this font, you have to setup webpack to correctly load.</p>

      <p>If you using easy installation (Vue.use), <b>you need to configure url-loader in webpack</b>. (Because webpack will try to use load font files)</p>

      <div class="row">
        <div class="col-sm-6">
          <b>WebPack 2.X</b>
          <doc-code language="javascript">
            $ npm install url-loader
          </doc-code>
          <doc-code language="javascript">
            {
              module:
              {
                test: /\.(woff2?|eot|ttf|otf)(\?.*)?$/,
                loader: 'url-loader', // you need to install this loader
                query: {
                  limit: 10000,
                  name: 'fonts/[name].[ext]'
                }
              }
            }
          </doc-code>
        </div>
        <div class="col-sm-6">
          <b>WebPack 1.X</b>
          <doc-code language="javascript">
            module: {
              loaders: [
                {
                  test: /\.woff2?(\?v=[0-9]\.[0-9]\.[0-9])?$/,
                  // Limiting the size of the woff fonts breaks font-awesome ONLY for the extract text plugin
                  // loader: "url?limit=10000"
                  loader: "url"
                },
                {
                  test: /\.(ttf|eot|svg)(\?[\s\S]+)?$/,
                  loader: 'file'
                },
              ]
            },
          </doc-code>
        </div>
      </div>

      <hr>

      <h3>Import bootue system into your project (<span class="text-success">recomended</span>)</h3>
      <p>
        We recommend to download all components files and import inside to project, remember the goal is transfer all power
        to select, customize and extends to any scss parts to project.
        In deep, bootue is a reorganized boostrap splitting code, her have <code>SCSS Components</code>, <code>Js Components</code> and <code>Hybrid Components</code>.
      </p>
      <doc-code language="markdown">
        //strutucture folder to generic vue 2 project
        - vuex
        - components
          - pages
            - home
            - contact
          - bootue
            - _core
            - grids
            - typography
            - utilities
            - index.js // use to make import components easy
      </doc-code>

      <p>We import bootue components aside page's project, the ideia its full integration scss rules into project.</p>

      <hr/>

      <div class="panel panel-primary">
        <div class="panel-heading">
          <h5 class="panel-title text-center">Why should I care about this structure? Why not use NPM?</h5>
        </div>

        <div class="panel-body">
          <p>When I began bootue, my problem is, I have a very custom layouts in any SPA project, but all the elements in its excence its the same. i would like exist a central repository with self  contanied elements, dont bother me with import scss bases, navigate and change 1000 lines in variables.scss, i like to get and put that element and works.</p>
          <hr/>
          <p>With that mind, the project intent to, split and organized all business logic's of bootstrap, possibility to choose and modify exacly parts i want, possibility to export the module for other projects using a top contained delivery, and possibility to using 100% component tree system modules</p>
          <hr/>
          <p>And updates? Come on, you execute a update your bootstrap frequently? Boostrap 3 update frequently?
The risk exist, bootue needs to bug fix, him will update, for this situation you need to copy and paste parcially, yes its not a best situation, but in moment its acceptable.</p>
        </div>
      </div>
    </doc-section>

    <doc-section id="im-folder" name="Important folders">
      <p>Bootue have a one very important folder, its called <code>_core</code>, inside we have all shared .scss, and components.
      </p>
      <doc-code language="javascript">
        //minimal worked
        - bootue
          - _core
            - _mixins // a lot of shared's mixins

            - _variables
              - _colors.scss // this its the most important file, all variable colors
              - _assets_helpers.scss
              - _forms.scss // size, height and width forms components
              - _grid.scss // variable grid (using in all components)
              - _screens.scss
              - _states.scss // colors states, like error, warning, success and primary
              - _typography.scss // typography
              - _zindex.scss // utils

            - components // a bunch of SCSSS Components
              - print // print rules
              - normalize
              - component-animation
              - responsive // responsive rules
              - scaffolding // reset rules
      </doc-code>
      <hr/>
      <div class="panel panel-primary">
        <div class="panel-heading">
          <h5 class="panel-title text-center">You maybe create a new components, your change anything, <br/>remember,
            bootue goal its organize and make easy to change any part of boostrap.</h5>
        </div>

        <div class="panel-body">
          <p>Maybe anothers importants folders is</p>
          <ul>
            <li><b>grid</b> - Grid system</li>
            <li><b>typograph</b> - Font files</li>
            <li><b>utilities</b> - Common scss utilities, like pull-left</li>
          </ul>
          <p>Its a SCSS Components, theses guys have only scss.</p>

        </div>
      </div>
    </doc-section>

    <doc-section id="organization" name="Variables and organization">
      <p>All global variables its inside <code>_core</code>
        folder, but each components have yours own variables, example:</p>
      <h5>Badges Component</h5>
      <doc-code>
        //folder structured
        - badges
          - _variables
            _variables.scss // all badges's variables

        Badges.vue
        style.scss // scss badges, import to boostrap
        template.html // template html component
      </doc-code>
      <p>Look hers variables</p>
      <doc-code language="css">
        @import '../../_core/variables'; // base colors

        $badge-color: #fff !default;
        //** Linked badge text color on hover
        $badge-link-hover-color: #fff !default;
        $badge-bg: $gray-light !default;

        //** Badge text color in active nav link
        $badge-active-color: $link-color !default;
        //** Badge background color in active nav link
        $badge-active-bg: #fff !default;

        $badge-font-weight: bold !default;
        $badge-line-height: 1 !default;
        $badge-border-radius: 10px !default;
      </doc-code>

    </doc-section>

    <doc-section id="v-model" name="v-model">
      <p>According to the vue2 specifications, <code>twoWay</code> binding is not supported anymore, except for <code>v-model</code>.
      </p>
      <p>The <code>v-model</code> directive in a component always link to <code>value</code> attribute.</p>
      <p>Keep in mind that in vue2:</p>
      <doc-code>
        &lt;!-- using v-model like this: -->
        &lt;component v-model="element">&lt;/component>
        &lt;!-- is the same that: -->
        &lt;component :value="element" @input="element = argument[0]">&lt;/component>
      </doc-code>
    </doc-section>
  </div>
</template>
<script>
  import docCode from '../../example/utils/docCode.js'
  import docSection from '../../example/utils/docSection.vue'
  export default {
    components: {
      docCode,
      docSection
    }
  }
</script>
