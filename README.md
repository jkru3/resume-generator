# tutorial
https://www.linkedin.com/posts/jkru3_swe-is-more-competitive-than-ever-to-stand-activity-7303839488642859008-zxOz?utm_source=share&utm_medium=member_desktop&rcm=ACoAAB7uMq4Bg5eKFlzETKS-OVhLvmaJK48qNY4

# background
SWE is more competitive than ever. To stand out, you need a resume that is easy to share with your network and targeted to the companies you want to work for.

suppose there is a section on your resume that you use everywhere. Maybe you need to make a change. If you are tailoring your resumes, you might have dozens --or hundreds-- of different CVs. Wouldn't it be nice to have a system manage all that?

this repo lets you do that. Fork it, and start making your own modules. You control everything. The best part is, you can host your pdfs on github pages and make links to every resume you publish.

# setup

`assets/`: this folder is a place to include .pdf documents of projects or research you have worked on. The links can be deployed through this repo on GH pages, which you can refer to in your resume
   
`build/`: LaTeX templates will be built here

`copy_pdf.py`: this script converts the built pdf into one renamed as whatever you have on the header comment in your `templates/` dir. 

`icons/`: what better way to tell the person reading your resume you are serious about their company specifically than embedding their icon in the resume directly?


```
├── modules
│   ├── experiences
│   ├── projects
│   └── skills
│       ├── backend
│       ├── frontend
│       ├── general
│       ├── ml
│       └── pm
```
`modules/`: the .tex files in `templates/` consume files in `modules/`. I've subdivided them into `experiences/`, `projects/` and `skills/`. You can add more

`pdfs`: this is where all your finalized resumes will be stored. Remember to name each one uniquely!

```
└── templates
    ├── (General)
    │   ├── BackEnd.tex
    │   ├── CoverLetter.tex
    │   ├── FrontEnd.tex
    │   ├── FullStack.tex
    │   ├── ML.tex
    │   └── styling.sty
    └── base-styling.sty
```
`templates/`: you can make a subdirectory for each company you are specializing a resume for. You can also have more than one resume for that company, as seen in the `(General)/` sub. Note that `base-styling.sty` will apply styling to ALL resumes, and each company should have it's own version of `styling.sty` (which applies custom colors and icons to them)

## requirements
python 3.8+
run `brew install texlive`
install the 'LaTeX workshop' VScode extension

## Usage
create resume templates and then save them. With LaTeX workshop, they are automatically compiled into PDFs

deploying a fork of this repo through GitHub pages will allow you to refer to any of the PDFs in the `pdf/` directory as a link, so anyone you want to share a tailored resume with can see it!

# resume tips:
for experience and skills module, it's good to follow the form:
1. Accomplished X
2. Measured by Y
3. By doing Z

there is plenty of advice online on making better technical resumes. I endorse the following:
- https://www.reddit.com/r/EngineeringResumes/wiki/index/?share_id=JPpfQ581Ep7v7Hk6Gl3pd&utm_content=1&utm_medium=ios_app&utm_name=ioscss&utm_source=share&utm_term=1#wiki_disclaimer.3A_your_submission_will_get_taken_down_if_you_do_not_read_this_wiki.
- https://thetechresume.com/samples/ats-myths-busted
- https://www.levels.fyi/blog/applying-star-method-resumes.html
- https://resumegenius.com/blog/resume-help/star-method-resume
- https://www.inc.com/bill-murphy-jr/google-recruiters-say-these-5-resume-tips-including-x-y-z-formula-will-improve-your-odds-of-getting-hired-at-google.html
- https://elevenrecruiting.com/create-an-effective-resume-xyz-resume-format/
- https://ca.indeed.com/career-advice/resumes-cover-letters/challenge-action-result-resume
- https://www.topresume.com/career-advice/how-to-get-more-results-with-a-car-resume

## Cover letters
some companies ask for cover letters. Since they aren't usually necessary, there is only one template for them. If you do feel like it's good to make one, you can save a lot of time copy/pasting your resume into a LLM with the following prompt

```
Here is my resume:
Here is my job:
Make me a narrative driven cover letter. Make me sound like a young upstart who they can see in themselves, and that whoever is reading this might want to take a chance on me.
```