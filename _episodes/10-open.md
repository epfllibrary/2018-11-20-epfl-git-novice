---
title: Open Science
teaching: 5
exercises: 0
questions:
- "How can version control help me make my work more open?"
objectives:
- "Explain how a version control system can be leveraged as an electronic lab notebook for computational work."
- "Explain why adding licensing information to a repository is important."
- "Choose a proper license."
- "Make your work easy to cite"
- "Explain different options for hosting scientific work."
keypoints:
- "Make your work easy to cite"
- "Open scientific work is more useful and more highly cited than closed."
- "People who incorporate General Public License (GPL'd) software into their own software must make their software also open under the GPL license; most other open licenses do not require this."
- "The Creative Commons family of licenses allow people to mix and match requirements and restrictions on attribution, creation of derivative works, further sharing, and commercialization."
- "People who are not lawyers should not try to write licenses from scratch."
- "Projects can be hosted on university servers, on personal domains, or on public forges."
- "Rules regarding intellectual property and storage of sensitive information apply no matter where code and data are hosted."
---

## Open science

Free sharing of information might be the ideal in science,
but the reality is often more complicated.
With open publication the process might like this:

*   The data that the scientist collects is stored in an open access repository
    like [figshare](https://figshare.com/) or
    [Zenodo](https://zenodo.org), possibly as soon as it's collected,
    and given its own
    [Digital Object Identifier](https://en.wikipedia.org/wiki/Digital_object_identifier) (DOI).
    Or the data was already published and is stored in
    [Dryad](https://datadryad.org/).
*   The scientist creates a new repository on GitHub to hold her work.
*   As she does her analysis,
    she pushes changes to her scripts
    (and possibly some output files)
    to that repository.
    She also uses the repository for her paper;
    that repository is then the hub for collaboration with her colleagues.
*   When she's happy with the state of her paper,
    she posts a version to [arXiv](https://arxiv.org/)
    or some other preprint server
    to invite feedback from peers.
*   Based on that feedback,
    she may post several revisions
    before finally submitting her paper to a journal.
*   The published paper includes links to her preprint
    and to her code and data repositories,
    which  makes it much easier for other scientists
    to use her work as starting point for their own research.


## License

When a repository with source code, a manuscript or other creative
works becomes public, it should include a file `LICENSE` or
`LICENSE.txt` in the base directory of the repository that clearly
states under which license the content is being made available. This
is because creative works are automatically eligible for intellectual
property (and thus copyright) protection. Reusing creative works
without a license is dangerous, because the copyright holders could
sue you for copyright infringement.

A license solves this problem by granting rights to others (the
licensees) that they would otherwise not have. What rights are being
granted under which conditions differs, often only slightly, from one
license to another. In practice, a few licenses are by far the most
popular, and [choosealicense.com](https://choosealicense.com/) will
help you find a common license that suits your needs.  Important
considerations include:

* Whether you want to address patent rights.
* Whether you require people distributing derivative works to also
  distribute their source code.
* Whether the content you are licensing is source code.
* Whether you want to license the code at all.

Choosing a license that is in common use makes life easier for
contributors and users, because they are more likely to already be
familiar with the license and don't have to wade through a bunch of
jargon to decide if they're ok with it.  The [Open Source
Initiative](https://opensource.org/licenses) and [Free Software
Foundation](https://www.gnu.org/licenses/license-list.html) both
maintain lists of licenses which are good choices.

At the end of the day what matters is that there is a clear statement
as to what the license is. Also, the license is best chosen from the
get-go, even if for a repository that is not public. Pushing off the
decision only makes it more complicated later, because each time a new
collaborator starts contributing, they, too, hold copyright and will
thus need to be asked for approval once a license is chosen.

## Citation

You may want to include a file called `CITATION` or `CITATION.txt`
that describes how to reference your project;
the [one for Software
Carpentry](https://github.com/swcarpentry/website/blob/gh-pages/CITATION)
states:

~~~
To reference Software Carpentry in publications, please cite both of the following:

Greg Wilson: "Software Carpentry: Getting Scientists to Write Better
Code by Making Them More Productive".  Computing in Science &
Engineering, Nov-Dec 2006.

Greg Wilson: "Software Carpentry: Lessons Learned". arXiv:1307.5448,
July 2013.

@article{wilson-software-carpentry-2006,
    author =  {Greg Wilson},
    title =   {Software Carpentry: Getting Scientists to Write Better Code by Making Them More Productive},
    journal = {Computing in Science \& Engineering},
    month =   {November--December},
    year =    {2006},
}

@online{wilson-software-carpentry-2013,
  author      = {Greg Wilson},
  title       = {Software Carpentry: Lessons Learned},
  version     = {1},
  date        = {2013-07-20},
  eprinttype  = {arxiv},
  eprint      = {1307.5448}
}
~~~
{: .source}

More detailed advice, and other ways to make your code citable can be found
[at the Software Sustainability Institute blog](https://www.software.ac.uk/how-cite-and-describe-software) and in:

>  Smith AM, Katz DS, Niemeyer KE, FORCE11 Software Citation Working Group.
>  (2016) Software citation principles. [PeerJ Computer Science 2:e86](https://peerj.com/articles/cs-86/) https://doi.org/10.7717/peerj-cs.86

There is also an [`@software{…`](https://www.google.de/search?q=git+citation+%22%40software%7B%22)
[BibTeX](https://www.ctan.org/pkg/bibtex) entry type in case
no "umbrella" citation like a paper or book exists for the project you want to
make citable.

## Hosting

You can use a public hosting service like
[GitHub](https://github.com), [GitLab](https://gitlab.com),or
[BitBucket](https://bitbucket.org).
Each of these services provides a web interface that enables people to create,
view, and edit their code repositories.  These services also provide
communication and project management tools including issue tracking, wiki pages,
email notifications, and code reviews.  These services benefit from economies of
scale and network effects: it's easier to run one large service well than to run
many smaller services to the same standard.  It's also easier for people to
collaborate.  Using a popular service can help connect your project with
communities already using the same service.

Swiss academics can also used [c4science](https://www.c4science.ch) which is managed by non-profit organization paid by the Swiss confederation.  

You may also want to check if the lab, the department, or the
university provide a hosting server, manage accounts and backups, and so on.  The
main benefit of this is that it clarifies who owns what, which is particularly
important if any of the material is sensitive (i.e., relates to experiments
involving human subjects or may be used in a patent application).
