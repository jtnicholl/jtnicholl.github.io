---
layout: default
---

[Back To Home](index.md)

# Assessment AI

<figure>
	<a href="/assets/images/assessment0.png" target="blank">
		<img height="74" width="150" src="/assets/images/assessment0_thumb.png" />
	</a>
	<figcaption>The Assessment AI's findings displayed in a web application</figcaption>
</figure>

While employed at Cosairus, I developed an API service using Django and spaCy which could be sent
text, which it would analyze and search in for sensitive medical information, such as mentions of
substance abuse and STDs. These findings would be reported back to the caller.

The service was then rewritten as a headless CLI application that processes a set of files. After
this was completed the project was handed back to me and I implemented several additional features.
These included accessing files from an API, extracting text automatically from PDF files, storing
results to a SQL database, creating and uploading an annotated version of the PDF file with the
sensitive information highlighted for review, detecting commingled records from multiple patients,
and detecting release authorization forms.

I also created a system where human QA reviewers can provide feedback on the AI's findings. This
feedback was saved and displayed in an administration application, where it can be approved or
rejected by a manager. After a process has received approved feedback, it can be submitted for
retraining.

Once this happens, a Python service retrieves the information from the database about the
AI's initial findings and the approved feedback, redownloads the searchable PDF file to extract its
text, and generates newly refined training data in an automated process.

<ul class="gallery">
	<li>
		<a href="/assets/images/assessment1.png" target="blank">
			<img src="/assets/images/assessment1_thumb.png" height="73" width="150" />
			<span>Completed processes with reviewer feedback</span>
		</a>
	</li>
	<li>
		<a href="/assets/images/assessment2.png" target="blank">
			<img src="/assets/images/assessment2_thumb.png" height="73" width="150" />
			<span>Manager approving or rejecting feedback, with the assessed document visible</span>
		</a>
	</li>
</ul>
