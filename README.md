# hugoMinimalTestTheme
A minimum test theme to generate the full site of unstyled pages for https://github.com/gohugoio/hugoBasicExample

## Usage

1. Clone a site, for example hugoBasicExample and switch to it
   ```
   git clone https://github.com/gohugoio/hugoBasicExample
   cd hugoBasicExample
   ```
2. Make a themes directory and switch to it
   ```
   mkdir themes
   cd themes
   ```
3. Add hugoMinimalTestTheme as a submodule
   ```
   git submodule add -f https://github.com/danielfdickinson/hugoMinimalTestTheme.git hugoMinimalTestTheme
   ```
4. Commit the change
   ```
   git add ..
   git commit -m "Add hugoMinimalTestTheme as a submodule"
   ```
5. To test the result, run the local Hugo server
   ```
   hugo server -t hugoMinimalTestTheme -b http://localhost:1313/
   ```
 
 Enjoy!
 
