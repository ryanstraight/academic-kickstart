# in .Rprofile of the website project
if (file.exists("~/.Rprofile")) {
  base::sys.source("~/.Rprofile", envir = environment())
}

# Blogdown options
options(
  blogdown.author = "ryan",
  blogdown.ext = ".Rmd",
  blogdown.subdir = "post",
  blogdown.yaml.empty = TRUE,
  blogdown.new_bundle = TRUE,
  blogdown.title_case = TRUE
)

# Setting prompt for session identification
options(prompt = "rs.com> ")

# Show a silly quote when it starts up
if(interactive())
  try(fortunes::fortune(), silent = TRUE)

