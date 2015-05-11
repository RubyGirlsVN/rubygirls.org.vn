desc "Commit the latest version of the site to the gh-pages branch"
task :deploy do
  site = `git ls-tree -d HEAD site | awk '{print $3}'`.strip
  new_commit = `echo 'Update site' | git commit-tree #{site} -p refs/heads/gh-pages`.strip
  `git update-ref refs/heads/gh-pages #{new_commit}`
  `git push origin gh-pages -f`
end
