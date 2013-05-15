

FF_BINARY = File.join('./FontForge.app', 'Contents', 'Resources', 'opt', 'local', 'bin', 'fontforge')

task :default do
  puts "Usage:"
  puts "======================"
  puts "FILE=fonts/SourceSansPro-SemiboldIt-webfont.ttf rake ff:name"
  puts ""
  puts "Tasks:"
  puts "======================"
  puts `rake -T`
  puts "\nReadme:"
  puts "======================"
  puts File.read('README.md')
end

namespace :ff do

  desc "Print font name"
  task :name do
    script("name")
  end
  
  desc "Print font family"
  task :family do
    puts script("family")
  end  

  desc "Print font weight"
  task :weight do
    puts script("weight")
  end

  desc "Print font ems"
  task :em do
    puts script("em")
  end

  desc "Print font vendor ID"
  task :vendor_id do
    puts script("vendor-id")
  end

  desc "Print characters in font"
  task :characters do
    puts script("characters")
  end

  desc "Prepares a TTF file for the web - optional `autohint=true` arg."
  # Usage: FILE="fonts/Idealist Sans.ttf" autohint=true rake ff:webfont_prep
  task :webfont_prep do
    puts script("webfont-prep", "#{'-autohint' if ENV['autohint']}")

    `mkdir output` unless File.exists?('output') 
    ext  = File.extname(ENV['FILE'])
    base = File.basename(ENV['FILE'], ext)
    `mv "fonts/#{base}-webfont#{ext}" output/`
  end

  desc "Print FontForge info"
  task :fontforge_info do
    puts script("info")
  end

end

def script(name, *args)
  `#{FF_BINARY} -script "scripts/#{name}.pe" "#{ENV['FILE']}" #{args.join(' ')}`
end