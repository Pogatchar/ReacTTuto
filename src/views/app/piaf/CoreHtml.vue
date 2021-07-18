<template>
  <div>
    <b-row>
      <b-colxx xxs="12">
        <piaf-breadcrumb :heading="$t('menu.start')" />
        <div class="separator mb-5"></div>
      </b-colxx>
    </b-row>
    <b-row>
      <b-colxx xxs="12">
        <b-card class="mb-4" :title="$t('menu.start')">
          <div class="root">
     <div class="container">
          <ul class="progressbar">
            <li class="active">Start with React</li>
            <li >Step 2</li>
            <li>Step 3</li>
            <li>Step 4</li>
            <li>Step 5</li>
            <li>Step 6</li>
            <li>Step 7</li>
            <li>Step 8</li>

          </ul>
      </div>
          <h1 class="title1">Étape 1 : ajouter un conteneur DOM à votre HTML</h1>
          <p class="dark mb-0">
            Pour commencer, ouvrez la page HTML que vous souhaitez modifier.
            Ajoutez une balise {{ ddiv }} vide pour indiquer l’endroit dans
            lequel vous souhaitez afficher quelque chose avec React. Par exemple
            :
          </p>
          <div class="ql-container ql-snow">
            <div class="ql-editor">
              <pre class="ql-syntax" spellcheck="false">

&lt;!-- ... code HTML existant ... --&gt;
&lt;div id="like_button_container"&gt;&lt;/div&gt;
&lt;!-- ... code HTML existant ... --&gt;
          </pre
              >
            </div>
          </div>
          <h1>Étape 2 : ajouter les balises de script</h1>
          <p class="dark mb-0">
            Ensuite, ajoutez trois balises {{ sscript }} à votre page HTML,
            juste avant la fermeture de la balise {{ bbody }} :
          </p>
          <div class="ql-container ql-snow">
            <div class="ql-editor">
              <pre class="ql-syntax" spellcheck="false">
 &lt;!-- ... autres contenus HTML ... --&gt;

  &lt;!-- Charge React --&gt;
  &lt;!-- Remarque : pour le déploiement, remplacez "development.js"
       par "production.min.js" --&gt;
  &lt;script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin&gt;&lt;/script&gt;
  &lt;script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin&gt;&lt;/script&gt;

  &lt;!-- Charge notre composant React --&gt;
  &lt;script src="like_button.js"&gt;&lt;/script&gt;
&lt;/body&gt;

</pre
              >
              
          
  </div>
  
            </div>
          </div>


           
        </b-card>
      </b-colxx>
    </b-row>
  </div>
</template>
 
<style scoped>
.container{
     width: 180%;
    position: relative;
    z-index: 1;
    margin-top: 20px;
   
}
.progressbar{
  counter-reset: step;
  list-style:none;
    

}
.progressbar li{
  float: left;
  width: 11.28%;
  position: relative;
  text-align: center;
}
.progressbar li:before{
  content:counter(step);
  counter-increment: step;
  width: 30px;
  height: 30px;
  border: 2px solid #bebebe;
  display: block;
  margin: 0 auto 10px auto;
  border-radius: 50%;
  line-height: 27px;
  background: white;
  color: #bebebe;
  text-align: center;
  font-weight: bold;
}
.progressbar li:after{
  content: '';
  position: absolute;
  width:100%;
  height: 3px;
  background: #979797;
  top: 15px;
  left: -50%;
  z-index: -1;
}
.progressbar li.active:before{
 border-color: #3aac5d;
 background: #3aac5d;
 color: white
}
.progressbar li.active:after{
 background: #3aac5d;
}
.progressbar li.active - li:after{
 background: #3aac5d;
}
.progressbar li.active - li:before{
border-color: #3aac5d;
background: #3aac5d;
color: white
}
.progressbar li:first-child:after{
 content: none;
}
.title1 {
  margin-top: 80px;
}
 
</style>


<script>
import stepProgress from './stepProgessSlider'
export default {
  components:{
    stepProgress
  }
}
</script>

<script>
import { VueEditor } from "vue2-editor";

export default {
  components: {
    VueEditor,
  },

  data() {
    return {
      ddiv: `<div>`,
      sscript: `<script>`,
      bbody: `</body>`,
    };
  },

  methods: {
    setEditorContent: function () {
      this.htmlForEditor = "<h1>Html For Editor</h1>";
    },
  },
};
</script>