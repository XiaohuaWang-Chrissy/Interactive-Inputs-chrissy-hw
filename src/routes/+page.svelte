<!--
@component
This is your page!
-->
<script>
  // Import all the news furniture components
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import CatDogCost from '$lib/components/CatCost.svelte';
  import DogCost from '$lib/components/DogCost.svelte';


  // Article metadata
  let headline = 'Pet Ownership Statistics';
  let byline = 'Written By Michelle Megna; Fact Checked By Korrena Bailie';
  let pubDate = '2026-02-06';

  // Related stories
  const relatedStories = [
    { headline: 'How America\'s top news organizations escape rigid publishing systems to design beautiful data-driven stories on deadline.', href: 'https://palewi.re/docs/coding-the-news/' },
    { headline: 'How to install, configure and use Visual Studio Code, GitHub and Copilot', href: 'https://palewi.re/docs/coding-the-news/scripts/week-1/' },
    { headline: "How to publish a website with Node.JS and GitHub Actions", href:"https://palewi.re/docs/coding-the-news/scripts/week-2/"},
  ];
</script>

<!-- This sets the page title in the browser tab -->
<svelte:head>
  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined." />
</svelte:head>

<!-- Your page content goes here -->
<div class="container">
  
  <!-- Article Header: Headline, byline, and publication date -->
  <ArticleHeader
    {headline}
    {byline}
    {pubDate}
  />

  <!-- Lead Image: Animated gif of students at the journalism school -->
  <Image
    src="/example-photo.gif"
    alt="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    caption="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    credit="Craig Newmark Graduate School of Journalism"
  />

  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
<p>Cost of Pet Ownership</p>

<p>While the love of a pet is priceless, the cost of owning one is not.</p>
<p>Veterinary care, grooming, food, treats and other outlays can add up quickly.</p>
<p>A Forbes Advisor analysis found that essential dog expenses cost an average of $1,533 annually.</p>

<p>This includes the cost of:</p>

<p>Dog boarding for a seven day vacation: $253</p>
<p>Veterinary care: $679.50</p>
<p>Pet insurance: $601.01</p>

<p>Dog owners who rely on doggy day care twice per week can expect to spend an additional $2,980 per year on average.</p>

<p>And if an unexpected vet bill pops up for a major incident, you can be on the hook for thousands of dollars—42% of pet owners say they can't cover a surprise vet bill of $999 or less without going into debt.</p>

<p>Pet insurance can partially reimburse you when you pay the bill for your pet's unexpected accidents and illnesses.</p>
<p>While you may not want to add another expense to your pet care costs, you might be surprised at how affordable pet insurance can be.</p>

<p>The average pet insurance cost for dogs is $44 a month, and the average pet insurance cost for cats is $30 a month, based on Forbes Advisor's analysis.</p>
<p>Having pet insurance is like putting a leash on your potential vet costs so they don't run out of control.</p>
<p>That can leave you with more money to spend on spoiling your furry companion.</p>

<p>Here's a closer look at the cost of pet ownership:</p>

<p>Dog owners spend the most on veterinary care ($367 per year), food ($339 per year) and grooming ($99 per year).</p>
<p>Cat owners spend the most on food ($310 per year), veterinary care ($253 per year) and toys ($50 per year).</p>
<p>Gen Z pet owners (ages 18 to 25) are the most likely to spoil their pets with birthday cakes (34%), birthday presents (39%) and clothing or costumes (32%).</p>
<p>Gen Z pet owners are also the most likely to spend money on behavioral training (41%), doggy daycare (35%), specialized pet food (44%) and dog walking services (31%).</p>
<CatDogCost />
<DogCost />
  </ArticleBody>

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />

</div>

<style>
  /* Styles here only apply to this page */
  .container {
    padding: var(--spacing-lg) var(--spacing-md);
  }
</style>