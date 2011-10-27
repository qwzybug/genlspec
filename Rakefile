
def jekyll(opts="", path="")
  sh "rm -rf _site"
  sh path + "jekyll " + opts
end

desc "Build site using Jekyll"
task :build do
  jekyll
end

desc "Serve on Localhost with port 4000"
task :default do
  jekyll "--server --auto"
end

desc "Serve on Localhost with port 4000 using development version"
task :unstable do
  jekyll "--server --auto", "/Users/d/Developer/jekyll/bin/"
end

desc "Deploy to Dev"
task :deploy => :"deploy:dev"

namespace :deploy do
  desc "Deploy to Dev"
  task :dev => :build do
    rsync "PREPRESS.generalspecificity.com"
  end
  
  desc "Deploy to Live"
  task :live => :build do
    rsync "generalspecificity.com"
  end
  
  desc "Deploy to Dev and Live"
  task :all => [:dev, :live]
  
  def rsync(domain)
    sh "rsync -rtz --delete _site/ doormouse.org:~/#{domain}/"
  end
end
