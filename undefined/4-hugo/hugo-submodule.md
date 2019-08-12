# Hugo가 적용될 Submodule 폴더 생성

Github에서 두 개의 Repository를 만든다.

blog - \(Main\)

naraewool.github.io - \(Hugo website\)

![](../../.gitbook/assets/image%20%2824%29.png)



그리고 main을 원격저장소로 지정하고 hugo website를 submodule로 등록한다.



![](../../.gitbook/assets/image%20%2814%29.png)

![](../../.gitbook/assets/image%20%2834%29.png)

계속 오류나더니 드디어 public 폴더가 생성되고 submodule로 지정되었다. 

![](../../.gitbook/assets/image%20%2829%29.png)



## submoduel이란?





> #### Step-by-step Instructions[ ](https://gohugo.io/hosting-and-deployment/hosting-on-github/#step-by-step-instructions) <a id="step-by-step-instructions"></a>
>
> 1. Create a `<YOUR-PROJECT>` \(e.g. `blog`\) repository on GitHub. This repository will contain Hugo’s content and other source files.
> 2. Create a `<USERNAME>.github.io` GitHub repository. This is the repository that will contain the fully rendered version of your Hugo website.
> 3. `git clone <YOUR-PROJECT-URL> && cd <YOUR-PROJECT>`
> 4. Paste your existing Hugo project into a new local `<YOUR-PROJECT>` repository. Make sure your website works locally \(`hugo server` or `hugo server -t <YOURTHEME>`\) and open your browser to [http://localhost:1313](http://localhost:1313/).
> 5. Once you are happy with the results:
>    * Press Ctrl+C to kill the server
>    * Before proceeding run `rm -rf public` to completely remove the `public` directory
> 6. `git submodule add -b master git@github.com:<USERNAME>/<USERNAME>.github.io.git public`. This creates a git [submodule](https://github.com/blog/2104-working-with-submodules). Now when you run the `hugo`command to build your site to `public`, the created `public` directory will have a different remote origin \(i.e. hosted GitHub repository\).

\(출처:[ Hugo 사이트](https://gohugo.io/hosting-and-deployment/hosting-on-github/#step-by-step-instructions)\)







