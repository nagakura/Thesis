task :default => ["clean","convert","all"]
task :all do
  system "platex    -kanji=utf8 main"
  system "pbibtex   -kanji=utf8 main"
  system "platex    -kanji=utf8 main"
  system "platex    -kanji=utf8 main"
  system "dvipdfmx  -p a4 main"
end
task :clean do
  system "/bin/rm -f *~ *.log *.dvi *.blg *.aux *.out *.bbl *.lot *.toc *.lof *.pdf *.eps"
end
task :convert do |t|
    Dir.glob("*.{jpg,png,gif}") {|f|
      r = f.gsub /\..+/, ".eps"
      system "convert #{f} #{r}"
      p "converted #{f} to #{r}"
    }
end
