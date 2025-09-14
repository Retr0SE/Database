
<!doctype html>
<html lang="uk" class="no-js">
  <head>
    
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width,initial-scale=1">
      
        <meta name="description" content="Повний курс з баз даних з лекціями, лабораторними роботами та презентаціями.">
      
      
        <meta name="author" content="Олександр Ройко">
      
      
        <link rel="canonical" href="https://olroi421.github.io/course-bd/labs/assets/lab01-report/">
      
      
      
      
      <link rel="icon" href="../../../assets/images/favicon.png">
      <meta name="generator" content="mkdocs-1.6.1, mkdocs-material-9.6.19">
    
    
      
        <title>Лабораторна робота 1. Робота з СУБД PostgreSQL та основи SQL - Бази даних</title>
      
    
    
      <link rel="stylesheet" href="../../../assets/stylesheets/main.7e37652d.min.css">
      
        
        <link rel="stylesheet" href="../../../assets/stylesheets/palette.06af60db.min.css">
      
      


    
    
      
    
    
      
        
        
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
        <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto:300,300i,400,400i,700,700i%7CRoboto+Mono:400,400i,700,700i&display=fallback">
        <style>:root{--md-text-font:"Roboto";--md-code-font:"Roboto Mono"}</style>
      
    
    
      <link rel="stylesheet" href="../../../stylesheets/extra.css">
    
    <script>__md_scope=new URL("../../..",location),__md_hash=e=>[...e].reduce(((e,_)=>(e<<5)-e+_.charCodeAt(0)),0),__md_get=(e,_=localStorage,t=__md_scope)=>JSON.parse(_.getItem(t.pathname+"."+e)),__md_set=(e,_,t=localStorage,a=__md_scope)=>{try{t.setItem(a.pathname+"."+e,JSON.stringify(_))}catch(e){}}</script>
    
      

    
    
    
  </head>
  
  
    
    
      
    
    
    
    
    <body dir="ltr" data-md-color-scheme="default" data-md-color-primary="blue" data-md-color-accent="blue">
  
    
    <input class="md-toggle" data-md-toggle="drawer" type="checkbox" id="__drawer" autocomplete="off">
    <input class="md-toggle" data-md-toggle="search" type="checkbox" id="__search" autocomplete="off">
    <label class="md-overlay" for="__drawer"></label>
    <div data-md-component="skip">
      
        
        <a href="#1-postgresql-sql" class="md-skip">
          Перейти до змісту
        </a>
      
    </div>
    <div data-md-component="announce">
      
    </div>
    
    
      

<header class="md-header" data-md-component="header">
  <nav class="md-header__inner md-grid" aria-label="Хедер">
    <a href="../../.." title="Бази даних" class="md-header__button md-logo" aria-label="Бази даних" data-md-component="logo">
      
  
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Free 7.0.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) Copyright 2025 Fonticons, Inc.--><path fill="currentColor" d="M448 205.8c-14.8 9.8-31.8 17.7-49.5 24-47 16.8-108.7 26.2-174.5 26.2s-127.6-9.5-174.5-26.2c-17.6-6.3-34.7-14.2-49.5-24V288c0 44.2 100.3 80 224 80s224-35.8 224-80zm0-77.8V80c0-44.2-100.3-80-224-80S0 35.8 0 80v48c0 44.2 100.3 80 224 80s224-35.8 224-80m-49.5 261.8C351.6 406.5 289.9 416 224 416s-127.6-9.5-174.5-26.2c-17.6-6.3-34.7-14.2-49.5-24V432c0 44.2 100.3 80 224 80s224-35.8 224-80v-66.2c-14.8 9.8-31.8 17.7-49.5 24"/></svg>

    </a>
    <label class="md-header__button md-icon" for="__drawer">
      
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M3 6h18v2H3zm0 5h18v2H3zm0 5h18v2H3z"/></svg>
    </label>
    <div class="md-header__title" data-md-component="header-title">
      <div class="md-header__ellipsis">
        <div class="md-header__topic">
          <span class="md-ellipsis">
            Бази даних
          </span>
        </div>
        <div class="md-header__topic" data-md-component="header-topic">
          <span class="md-ellipsis">
            
              Лабораторна робота 1. Робота з СУБД PostgreSQL та основи SQL
            
          </span>
        </div>
      </div>
    </div>
    
      
        <form class="md-header__option" data-md-component="palette">
  
    
    
    
    <input class="md-option" data-md-color-media="(prefers-color-scheme)" data-md-color-scheme="default" data-md-color-primary="blue" data-md-color-accent="blue"  aria-label="Перемкнути на світлу тему"  type="radio" name="__palette" id="__palette_0">
    
      <label class="md-header__button md-icon" title="Перемкнути на світлу тему" for="__palette_1" hidden>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="m14.3 16-.7-2h-3.2l-.7 2H7.8L11 7h2l3.2 9zM20 8.69V4h-4.69L12 .69 8.69 4H4v4.69L.69 12 4 15.31V20h4.69L12 23.31 15.31 20H20v-4.69L23.31 12zm-9.15 3.96h2.3L12 9z"/></svg>
      </label>
    
  
    
    
    
    <input class="md-option" data-md-color-media="(prefers-color-scheme: light)" data-md-color-scheme="default" data-md-color-primary="blue" data-md-color-accent="blue"  aria-label="Перемкнути на темну тему"  type="radio" name="__palette" id="__palette_1">
    
      <label class="md-header__button md-icon" title="Перемкнути на темну тему" for="__palette_2" hidden>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 8a4 4 0 0 0-4 4 4 4 0 0 0 4 4 4 4 0 0 0 4-4 4 4 0 0 0-4-4m0 10a6 6 0 0 1-6-6 6 6 0 0 1 6-6 6 6 0 0 1 6 6 6 6 0 0 1-6 6m8-9.31V4h-4.69L12 .69 8.69 4H4v4.69L.69 12 4 15.31V20h4.69L12 23.31 15.31 20H20v-4.69L23.31 12z"/></svg>
      </label>
    
  
    
    
    
    <input class="md-option" data-md-color-media="(prefers-color-scheme: dark)" data-md-color-scheme="slate" data-md-color-primary="blue" data-md-color-accent="blue"  aria-label="Перемкнути на автоматичну тему"  type="radio" name="__palette" id="__palette_2">
    
      <label class="md-header__button md-icon" title="Перемкнути на автоматичну тему" for="__palette_0" hidden>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 18c-.89 0-1.74-.2-2.5-.55C11.56 16.5 13 14.42 13 12s-1.44-4.5-3.5-5.45C10.26 6.2 11.11 6 12 6a6 6 0 0 1 6 6 6 6 0 0 1-6 6m8-9.31V4h-4.69L12 .69 8.69 4H4v4.69L.69 12 4 15.31V20h4.69L12 23.31 15.31 20H20v-4.69L23.31 12z"/></svg>
      </label>
    
  
</form>
      
    
    
      <script>var palette=__md_get("__palette");if(palette&&palette.color){if("(prefers-color-scheme)"===palette.color.media){var media=matchMedia("(prefers-color-scheme: light)"),input=document.querySelector(media.matches?"[data-md-color-media='(prefers-color-scheme: light)']":"[data-md-color-media='(prefers-color-scheme: dark)']");palette.color.media=input.getAttribute("data-md-color-media"),palette.color.scheme=input.getAttribute("data-md-color-scheme"),palette.color.primary=input.getAttribute("data-md-color-primary"),palette.color.accent=input.getAttribute("data-md-color-accent")}for(var[key,value]of Object.entries(palette.color))document.body.setAttribute("data-md-color-"+key,value)}</script>
    
    
    
      
      
        <label class="md-header__button md-icon" for="__search">
          
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M9.5 3A6.5 6.5 0 0 1 16 9.5c0 1.61-.59 3.09-1.56 4.23l.27.27h.79l5 5-1.5 1.5-5-5v-.79l-.27-.27A6.52 6.52 0 0 1 9.5 16 6.5 6.5 0 0 1 3 9.5 6.5 6.5 0 0 1 9.5 3m0 2C7 5 5 7 5 9.5S7 14 9.5 14 14 12 14 9.5 12 5 9.5 5"/></svg>
        </label>
        <div class="md-search" data-md-component="search" role="dialog">
  <label class="md-search__overlay" for="__search"></label>
  <div class="md-search__inner" role="search">
    <form class="md-search__form" name="search">
      <input type="text" class="md-search__input" name="query" aria-label="Пошук" placeholder="Пошук" autocapitalize="off" autocorrect="off" autocomplete="off" spellcheck="false" data-md-component="search-query" required>
      <label class="md-search__icon md-icon" for="__search">
        
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M9.5 3A6.5 6.5 0 0 1 16 9.5c0 1.61-.59 3.09-1.56 4.23l.27.27h.79l5 5-1.5 1.5-5-5v-.79l-.27-.27A6.52 6.52 0 0 1 9.5 16 6.5 6.5 0 0 1 3 9.5 6.5 6.5 0 0 1 9.5 3m0 2C7 5 5 7 5 9.5S7 14 9.5 14 14 12 14 9.5 12 5 9.5 5"/></svg>
        
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M20 11v2H8l5.5 5.5-1.42 1.42L4.16 12l7.92-7.92L13.5 5.5 8 11z"/></svg>
      </label>
      <nav class="md-search__options" aria-label="Шукати">
        
          <a href="javascript:void(0)" class="md-search__icon md-icon" title="Поділитись" aria-label="Поділитись" data-clipboard data-clipboard-text="" data-md-component="search-share" tabindex="-1">
            
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M18 16.08c-.76 0-1.44.3-1.96.77L8.91 12.7c.05-.23.09-.46.09-.7s-.04-.47-.09-.7l7.05-4.11c.54.5 1.25.81 2.04.81a3 3 0 0 0 3-3 3 3 0 0 0-3-3 3 3 0 0 0-3 3c0 .24.04.47.09.7L8.04 9.81C7.5 9.31 6.79 9 6 9a3 3 0 0 0-3 3 3 3 0 0 0 3 3c.79 0 1.5-.31 2.04-.81l7.12 4.15c-.05.21-.08.43-.08.66 0 1.61 1.31 2.91 2.92 2.91s2.92-1.3 2.92-2.91A2.92 2.92 0 0 0 18 16.08"/></svg>
          </a>
        
        <button type="reset" class="md-search__icon md-icon" title="Очистити" aria-label="Очистити" tabindex="-1">
          
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M19 6.41 17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"/></svg>
        </button>
      </nav>
      
    </form>
    <div class="md-search__output">
      <div class="md-search__scrollwrap" tabindex="0" data-md-scrollfix>
        <div class="md-search-result" data-md-component="search-result">
          <div class="md-search-result__meta">
            Пошук розпочато
          </div>
          <ol class="md-search-result__list" role="presentation"></ol>
        </div>
      </div>
    </div>
  </div>
</div>
      
    
    
      <div class="md-header__source">
        <a href="https://github.com/olroi421/course-bd" title="Перейти до вихідного коду" class="md-source" data-md-component="source">
  <div class="md-source__icon md-icon">
    
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Free 7.0.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) Copyright 2025 Fonticons, Inc.--><path fill="currentColor" d="M439.6 236.1 244 40.5c-5.4-5.5-12.8-8.5-20.4-8.5s-15 3-20.4 8.4L162.5 81l51.5 51.5c27.1-9.1 52.7 16.8 43.4 43.7l49.7 49.7c34.2-11.8 61.2 31 35.5 56.7-26.5 26.5-70.2-2.9-56-37.3L240.3 199v121.9c25.3 12.5 22.3 41.8 9.1 55-6.4 6.4-15.2 10.1-24.3 10.1s-17.8-3.6-24.3-10.1c-17.6-17.6-11.1-46.9 11.2-56v-123c-20.8-8.5-24.6-30.7-18.6-45L142.6 101 8.5 235.1C3 240.6 0 247.9 0 255.5s3 15 8.5 20.4l195.6 195.7c5.4 5.4 12.7 8.4 20.4 8.4s15-3 20.4-8.4l194.7-194.7c5.4-5.4 8.4-12.8 8.4-20.4s-3-15-8.4-20.4"/></svg>
  </div>
  <div class="md-source__repository">
    olroi421/course-bd
  </div>
</a>
      </div>
    
  </nav>
  
</header>
    
    <div class="md-container" data-md-component="container">
      
      
        
          
            
<nav class="md-tabs" aria-label="Вкладки" data-md-component="tabs">
  <div class="md-grid">
    <ul class="md-tabs__list">
      
        
  
  
  
  
    <li class="md-tabs__item">
      <a href="../../.." class="md-tabs__link">
        
  
  
    
  
  Головна

      </a>
    </li>
  

      
        
  
  
  
  
    
    
      <li class="md-tabs__item">
        <a href="../../../lectures/" class="md-tabs__link">
          
  
  
  Лекції

        </a>
      </li>
    
  

      
        
  
  
  
  
    
    
      <li class="md-tabs__item">
        <a href="../../" class="md-tabs__link">
          
  
  
  Лабораторні роботи

        </a>
      </li>
    
  

      
        
  
  
  
  
    
    
      <li class="md-tabs__item">
        <a href="../../../presentations/" class="md-tabs__link">
          
  
  
  Презентації

        </a>
      </li>
    
  

      
    </ul>
  </div>
</nav>
          
        
      
      <main class="md-main" data-md-component="main">
        <div class="md-main__inner md-grid">
          
            
              
              <div class="md-sidebar md-sidebar--primary" data-md-component="sidebar" data-md-type="navigation" >
                <div class="md-sidebar__scrollwrap">
                  <div class="md-sidebar__inner">
                    


  


<nav class="md-nav md-nav--primary md-nav--lifted" aria-label="Навігація" data-md-level="0">
  <label class="md-nav__title" for="__drawer">
    <a href="../../.." title="Бази даних" class="md-nav__button md-logo" aria-label="Бази даних" data-md-component="logo">
      
  
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Free 7.0.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) Copyright 2025 Fonticons, Inc.--><path fill="currentColor" d="M448 205.8c-14.8 9.8-31.8 17.7-49.5 24-47 16.8-108.7 26.2-174.5 26.2s-127.6-9.5-174.5-26.2c-17.6-6.3-34.7-14.2-49.5-24V288c0 44.2 100.3 80 224 80s224-35.8 224-80zm0-77.8V80c0-44.2-100.3-80-224-80S0 35.8 0 80v48c0 44.2 100.3 80 224 80s224-35.8 224-80m-49.5 261.8C351.6 406.5 289.9 416 224 416s-127.6-9.5-174.5-26.2c-17.6-6.3-34.7-14.2-49.5-24V432c0 44.2 100.3 80 224 80s224-35.8 224-80v-66.2c-14.8 9.8-31.8 17.7-49.5 24"/></svg>

    </a>
    Бази даних
  </label>
  
    <div class="md-nav__source">
      <a href="https://github.com/olroi421/course-bd" title="Перейти до вихідного коду" class="md-source" data-md-component="source">
  <div class="md-source__icon md-icon">
    
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Free 7.0.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) Copyright 2025 Fonticons, Inc.--><path fill="currentColor" d="M439.6 236.1 244 40.5c-5.4-5.5-12.8-8.5-20.4-8.5s-15 3-20.4 8.4L162.5 81l51.5 51.5c27.1-9.1 52.7 16.8 43.4 43.7l49.7 49.7c34.2-11.8 61.2 31 35.5 56.7-26.5 26.5-70.2-2.9-56-37.3L240.3 199v121.9c25.3 12.5 22.3 41.8 9.1 55-6.4 6.4-15.2 10.1-24.3 10.1s-17.8-3.6-24.3-10.1c-17.6-17.6-11.1-46.9 11.2-56v-123c-20.8-8.5-24.6-30.7-18.6-45L142.6 101 8.5 235.1C3 240.6 0 247.9 0 255.5s3 15 8.5 20.4l195.6 195.7c5.4 5.4 12.7 8.4 20.4 8.4s15-3 20.4-8.4l194.7-194.7c5.4-5.4 8.4-12.8 8.4-20.4s-3-15-8.4-20.4"/></svg>
  </div>
  <div class="md-source__repository">
    olroi421/course-bd
  </div>
</a>
    </div>
  
  <ul class="md-nav__list" data-md-scrollfix>
    
      
      
  
  
  
  
    <li class="md-nav__item">
      <a href="../../.." class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Головна
    
  </span>
  

      </a>
    </li>
  

    
      
      
  
  
  
  
    
    
    
    
      
      
        
      
    
    
    <li class="md-nav__item md-nav__item--nested">
      
        
        
          
        
        <input class="md-nav__toggle md-toggle md-toggle--indeterminate" type="checkbox" id="__nav_2" >
        
          
          <label class="md-nav__link" for="__nav_2" id="__nav_2_label" tabindex="0">
            
  
  
  <span class="md-ellipsis">
    Лекції
    
  </span>
  

            <span class="md-nav__icon md-icon"></span>
          </label>
        
        <nav class="md-nav" data-md-level="1" aria-labelledby="__nav_2_label" aria-expanded="false">
          <label class="md-nav__title" for="__nav_2">
            <span class="md-nav__icon md-icon"></span>
            Лекції
          </label>
          <ul class="md-nav__list" data-md-scrollfix>
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../lectures/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    📚 Лекції
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../lectures/lecture-01/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Лекція 1. Еволюція систем управління даними
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../lectures/lecture-02/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Лекція 2. Архітектура систем управління базами даних
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../lectures/lecture-03/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Лекція 3. Моделі представлення даних
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../lectures/lecture-04/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Лекція 4. Реляційна модель даних
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../lectures/lecture-05/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Лекція 5. Концептуальне моделювання предметних областей
    
  </span>
  

      </a>
    </li>
  

              
            
          </ul>
        </nav>
      
    </li>
  

    
      
      
  
  
  
  
    
    
    
    
      
      
        
      
    
    
    <li class="md-nav__item md-nav__item--nested">
      
        
        
          
        
        <input class="md-nav__toggle md-toggle md-toggle--indeterminate" type="checkbox" id="__nav_3" >
        
          
          <label class="md-nav__link" for="__nav_3" id="__nav_3_label" tabindex="0">
            
  
  
  <span class="md-ellipsis">
    Лабораторні роботи
    
  </span>
  

            <span class="md-nav__icon md-icon"></span>
          </label>
        
        <nav class="md-nav" data-md-level="1" aria-labelledby="__nav_3_label" aria-expanded="false">
          <label class="md-nav__title" for="__nav_3">
            <span class="md-nav__icon md-icon"></span>
            Лабораторні роботи
          </label>
          <ul class="md-nav__list" data-md-scrollfix>
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    🧪 Лабораторні роботи
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../lab-01/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Лабораторна робота 1. Робота з СУБД PostgreSQL та основи SQL
    
  </span>
  

      </a>
    </li>
  

              
            
          </ul>
        </nav>
      
    </li>
  

    
      
      
  
  
  
  
    
    
    
    
      
      
        
      
    
    
    <li class="md-nav__item md-nav__item--nested">
      
        
        
          
        
        <input class="md-nav__toggle md-toggle md-toggle--indeterminate" type="checkbox" id="__nav_4" >
        
          
          <label class="md-nav__link" for="__nav_4" id="__nav_4_label" tabindex="0">
            
  
  
  <span class="md-ellipsis">
    Презентації
    
  </span>
  

            <span class="md-nav__icon md-icon"></span>
          </label>
        
        <nav class="md-nav" data-md-level="1" aria-labelledby="__nav_4_label" aria-expanded="false">
          <label class="md-nav__title" for="__nav_4">
            <span class="md-nav__icon md-icon"></span>
            Презентації
          </label>
          <ul class="md-nav__list" data-md-scrollfix>
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../presentations/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    📊 Презентації
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../presentations/presentation-01/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Еволюція систем управління даними
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../presentations/presentation-02/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Архітектура систем управління базами даних
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../presentations/presentation-03/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Моделі представлення даних
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../presentations/presentation-04/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Реляційна модель даних
    
  </span>
  

      </a>
    </li>
  

              
            
              
                
  
  
  
  
    <li class="md-nav__item">
      <a href="../../../presentations/presentation-05/" class="md-nav__link">
        
  
  
  <span class="md-ellipsis">
    Концептуальне моделювання предметних областей
    
  </span>
  

      </a>
    </li>
  

              
            
          </ul>
        </nav>
      
    </li>
  

    
  </ul>
</nav>
                  </div>
                </div>
              </div>
            
            
              
              <div class="md-sidebar md-sidebar--secondary" data-md-component="sidebar" data-md-type="toc" >
                <div class="md-sidebar__scrollwrap">
                  <div class="md-sidebar__inner">
                    

<nav class="md-nav md-nav--secondary" aria-label="Зміст">
  
  
  
    
  
  
    <label class="md-nav__title" for="__toc">
      <span class="md-nav__icon md-icon"></span>
      Зміст
    </label>
    <ul class="md-nav__list" data-md-component="toc" data-md-scrollfix>
      
        <li class="md-nav__item">
  <a href="#_1" class="md-nav__link">
    <span class="md-ellipsis">
      Загальна інформація
    </span>
  </a>
  
</li>
      
        <li class="md-nav__item">
  <a href="#_2" class="md-nav__link">
    <span class="md-ellipsis">
      Виконання завдань
    </span>
  </a>
  
    <nav class="md-nav" aria-label="Виконання завдань">
      <ul class="md-nav__list">
        
          <li class="md-nav__item">
  <a href="#_3" class="md-nav__link">
    <span class="md-ellipsis">
      Список таблиць
    </span>
  </a>
  
</li>
        
          <li class="md-nav__item">
  <a href="#customers" class="md-nav__link">
    <span class="md-ellipsis">
      Отримати всі записи з таблиці customers.
    </span>
  </a>
  
</li>
        
      </ul>
    </nav>
  
</li>
      
        <li class="md-nav__item">
  <a href="#_4" class="md-nav__link">
    <span class="md-ellipsis">
      Висновки
    </span>
  </a>
  
</li>
      
    </ul>
  
</nav>
                  </div>
                </div>
              </div>
            
          
          
            <div class="md-content" data-md-component="content">
              <article class="md-content__inner md-typeset">
                
                  


  
    <a href="https://github.com/olroi421/course-bd/edit/main/docs/labs/assets/lab01-report.md" title="Редагувати сторінку" class="md-content__button md-icon" rel="edit">
      
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M10 20H6V4h7v5h5v3.1l2-2V8l-6-6H6c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h4zm10.2-7c.1 0 .3.1.4.2l1.3 1.3c.2.2.2.6 0 .8l-1 1-2.1-2.1 1-1c.1-.1.2-.2.4-.2m0 3.9L14.1 23H12v-2.1l6.1-6.1z"/></svg>
    </a>
  
  
    
      
    
    <a href="https://github.com/olroi421/course-bd/raw/main/docs/labs/assets/lab01-report.md" title="Переглянути вихідний код сторінки" class="md-content__button md-icon">
      
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17 18c.56 0 1 .44 1 1s-.44 1-1 1-1-.44-1-1 .44-1 1-1m0-3c-2.73 0-5.06 1.66-6 4 .94 2.34 3.27 4 6 4s5.06-1.66 6-4c-.94-2.34-3.27-4-6-4m0 6.5a2.5 2.5 0 0 1-2.5-2.5 2.5 2.5 0 0 1 2.5-2.5 2.5 2.5 0 0 1 2.5 2.5 2.5 2.5 0 0 1-2.5 2.5M9.27 20H6V4h7v5h5v4.07c.7.08 1.36.25 2 .49V8l-6-6H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h4.5a8.2 8.2 0 0 1-1.23-2"/></svg>
    </a>
  


<h1 id="1-postgresql-sql">Лабораторна робота 1. Робота з СУБД PostgreSQL та основи SQL<a class="headerlink" href="#1-postgresql-sql" title="Permanent link">&para;</a></h1>
<h2 id="_1">Загальна інформація<a class="headerlink" href="#_1" title="Permanent link">&para;</a></h2>
<p><strong>Здобувач освіти:</strong> [Ваше ПІБ]
<strong>Група:</strong> [Номер групи]
<strong>Обраний рівень складності:</strong> [1/2/3]
<strong>Посилання на проєкт:</strong> [Посилання на Supabase проєкт]</p>
<h2 id="_2">Виконання завдань<a class="headerlink" href="#_2" title="Permanent link">&para;</a></h2>
<h3 id="_3">Список таблиць<a class="headerlink" href="#_3" title="Permanent link">&para;</a></h3>
<div class="highlight"><pre><span></span><code><a id="__codelineno-0-1" name="__codelineno-0-1" href="#__codelineno-0-1"></a><span class="c1">-- Запит для отримання списку таблиць</span>
<a id="__codelineno-0-2" name="__codelineno-0-2" href="#__codelineno-0-2"></a><span class="k">SELECT</span><span class="w"> </span><span class="k">table_name</span>
<a id="__codelineno-0-3" name="__codelineno-0-3" href="#__codelineno-0-3"></a><span class="k">FROM</span><span class="w"> </span><span class="n">information_schema</span><span class="p">.</span><span class="n">tables</span>
<a id="__codelineno-0-4" name="__codelineno-0-4" href="#__codelineno-0-4"></a><span class="k">WHERE</span><span class="w"> </span><span class="n">table_schema</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="s1">&#39;public&#39;</span>
<a id="__codelineno-0-5" name="__codelineno-0-5" href="#__codelineno-0-5"></a><span class="k">ORDER</span><span class="w"> </span><span class="k">BY</span><span class="w"> </span><span class="k">table_name</span><span class="p">;</span>
</code></pre></div>
<p>Результат: У базі даних створено 8 основних таблиць: categories, customers, employees, order_items, orders, products, regions, suppliers.</p>
<p>Скріншот</p>
<p>...</p>
<h3 id="customers">Отримати всі записи з таблиці customers.<a class="headerlink" href="#customers" title="Permanent link">&para;</a></h3>
<div class="highlight"><pre><span></span><code><a id="__codelineno-1-1" name="__codelineno-1-1" href="#__codelineno-1-1"></a><span class="k">SELECT</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="k">FROM</span><span class="w"> </span><span class="n">customers</span><span class="p">;</span>
</code></pre></div>
<p>Результат: Отримано 15 записів клієнтів, включаючи як фізичних осіб, так і юридичні особи з різних міст України.</p>
<p>Скріншот</p>
<p>[Продовжити для всіх завдань обраного рівня]</p>
<h2 id="_4">Висновки<a class="headerlink" href="#_4" title="Permanent link">&para;</a></h2>
<p><strong>Самооцінка</strong>: [ваша оцінка роботи, 3-5]</p>
<p><strong>Обгрунтування</strong>: [обґрунтування самооцінки]</p>












                
              </article>
            </div>
          
          
<script>var target=document.getElementById(location.hash.slice(1));target&&target.name&&(target.checked=target.name.startsWith("__tabbed_"))</script>
        </div>
        
          <button type="button" class="md-top md-icon" data-md-component="top" hidden>
  
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M13 20h-2V8l-5.5 5.5-1.42-1.42L12 4.16l7.92 7.92-1.42 1.42L13 8z"/></svg>
  Повернутись нагору
</button>
        
      </main>
      
        <footer class="md-footer">
  
    
  
  <div class="md-footer-meta md-typeset">
    <div class="md-footer-meta__inner md-grid">
      <div class="md-copyright">
  
    <div class="md-copyright__highlight">
      Copyright &copy; 2025 Олександр Ройко
    </div>
  
  
    Made with
    <a href="https://squidfunk.github.io/mkdocs-material/" target="_blank" rel="noopener">
      Material for MkDocs
    </a>
  
</div>
      
    </div>
  </div>
</footer>
      
    </div>
    <div class="md-dialog" data-md-component="dialog">
      <div class="md-dialog__inner md-typeset"></div>
    </div>
    
    
    
      
      <script id="__config" type="application/json">{"base": "../../..", "features": ["navigation.tabs", "navigation.sections", "navigation.expand", "navigation.path", "navigation.top", "navigation.footer", "search.highlight", "search.share", "content.code.copy", "content.code.annotate", "content.action.edit", "content.action.view", "content.print"], "search": "../../../assets/javascripts/workers/search.973d3a69.min.js", "tags": null, "translations": {"clipboard.copied": "\u0421\u043a\u043e\u043f\u0456\u0439\u043e\u0432\u0430\u043d\u043e \u0432 \u0431\u0443\u0444\u0435\u0440", "clipboard.copy": "\u0421\u043a\u043e\u043f\u0456\u044e\u0432\u0430\u0442\u0438 \u0432 \u0431\u0443\u0444\u0435\u0440", "search.result.more.one": "\u0429\u0435 1 \u0437\u0431\u0456\u0433 \u043d\u0430 \u0446\u0456\u0439 \u0441\u0442\u043e\u0440\u0456\u043d\u0446\u0456", "search.result.more.other": "\u0429\u0435 # \u0437\u0431\u0456\u0433\u0456\u0432 \u043d\u0430 \u0446\u0456\u0439 \u0441\u0442\u043e\u0440\u0456\u043d\u0446\u0456", "search.result.none": "\u0417\u0431\u0456\u0433\u0456\u0432 \u043d\u0435 \u0437\u043d\u0430\u0439\u0434\u0435\u043d\u043e", "search.result.one": "\u0417\u043d\u0430\u0439\u0434\u0435\u043d\u043e 1 \u0437\u0431\u0456\u0433", "search.result.other": "\u0417\u043d\u0430\u0439\u0434\u0435\u043d\u043e # \u0437\u0431\u0456\u0433\u0456\u0432", "search.result.placeholder": "\u0420\u043e\u0437\u043f\u043e\u0447\u043d\u0456\u0442\u044c \u043f\u0438\u0441\u0430\u0442\u0438 \u0434\u043b\u044f \u043f\u043e\u0448\u0443\u043a\u0443", "search.result.term.missing": "\u041d\u0435 \u0437\u043d\u0430\u0439\u0434\u0435\u043d\u043e \u0437\u0430\u043f\u0438\u0442\u0443", "select.version": "\u041e\u0431\u0440\u0430\u0442\u0438 \u0432\u0435\u0440\u0441\u0456\u044e"}, "version": null}</script>
    
    
      <script src="../../../assets/javascripts/bundle.92b07e13.min.js"></script>
      
    
  </body>
</html>