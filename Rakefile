
require "psych"

namespace "ppl" do

  namespace "web" do

    task :all => [:css]

    task :css do

      version = config("version")

      root = File.dirname(__FILE__)
      src  = File.join(root, "_stylesheets", "ppl", "*.less")
      dst  = File.join(root, "stylesheets", "ppl", "#{version}.css")

      matches = Dir.glob(src).join(" ")
      command = "lessc #{matches} > #{dst}"
      system(command)
    end

    task :html do
      system("jekyll")
    end

  end

end

def config(key)
  filename = File.dirname(__FILE__)
  filename = File.join(filename, "_config.yml")
  config   = Psych.load_file(filename)
  config[key]
end
