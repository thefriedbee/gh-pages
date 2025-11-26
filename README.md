## The steps for me to update the website

1. Use `npm run build` in command line to rebuild the app
2. commit and push everything to the main branch
3. Besides push the whole project, remember to commit and push the "dist" repository separately
4. commit the subtree to the "gh-pages" branch (`git subtree push --prefix dist origin gh-pages1`)
5. Wait for some minutes and refresh the website...
6. Consider the delete remote branch `git push origin --delete feature/login`
7. (you can delete local branch by `git branch -D local_branch_name`)!!!

