# 👿 Deep Fakes

## Technical Summary

Deep fakes refer to artificially manipulated videos or images in which an individual's face is replaced with someone else's face. The term "deep fake" comes from the use of deep learning techniques, specifically generative adversarial networks (GANs), to generate realistic-looking images or videos that are difficult to distinguish from real ones. In recent years, deep fakes have become a growing concern, as they have been used for various malicious purposes, such as spreading false information, manipulating political discourse, and conducting fraud.

Deep fakes are created using artificial intelligence (AI) algorithms, specifically GANs. GANs consist of two neural networks, a generator and a discriminator, that are trained together to generate realistic images or videos. The generator creates the fake images or videos, while the discriminator evaluates how realistic they are. Over time, the generator learns to create images or videos that are increasingly difficult for the discriminator to distinguish from real ones.

To create a deep fake, the generator is trained on a dataset of images or videos of the person whose face is going to be replaced. The generator learns to create a digital model of the person's face and then replaces the face in the original video or image with the generated face. The result is a video or image that looks like it was originally filmed with the replaced person's face.

Potential uses of deep fakes: While the technology behind deep fakes can be used for positive purposes, such as in the film industry or for educational purposes, there are concerns about the malicious uses of deep fakes. Some potential uses of deep fakes include:

1. Political manipulation: Deep fakes can be used to manipulate political discourse by creating fake videos of political leaders or candidates saying or doing things that they did not actually say or do.
2. Fraud: Deep fakes can be used to conduct fraud by creating fake videos of individuals claiming to be someone they are not, such as a bank CEO or a government official.
3. Revenge pornography: Deep fakes can be used to create fake videos or images of individuals engaging in sexual activities, which can be used to shame or blackmail them.
4. Misinformation: Deep fakes can be used to spread false information or conspiracy theories by creating fake videos or images that support a particular narrative.

Legal and ethical implications: The use of deep fakes raises several legal and ethical concerns. One concern is the potential for deep fakes to be used to harm individuals or organizations. For example, deep fakes could be used to damage the reputation of a political candidate or to conduct fraud against a business. This could result in significant financial or reputational damage.

Another concern is the potential for deep fakes to be used to spread false information or propaganda. Deep fakes could be used to manipulate public opinion, sow discord, or create confusion about what is real and what is not.

In response to these concerns, several countries have passed or are considering passing laws to regulate the use of deep fakes. For example, in the United States, several states have passed laws that make it illegal to create or distribute deep fakes for malicious purposes. Additionally, several social media platforms have implemented policies to detect and remove deep fakes from their platforms.

Deep fakes are a growing concern as the technology behind them becomes more sophisticated. While the technology can be used for positive purposes, such as in the film industry or for educational purposes, there are concerns about the malicious uses of deep fakes. The potential for deep fakes to be used to harm individuals or organizations, spread false information, or manipulate public opinion raises several legal and ethical concerns. As such, it is important to continue to monitor the development and use of deep fakes and to implement measures to prevent their malicious use.

### What is a deepfake? <a href="#what-is-a-deepfake" id="what-is-a-deepfake"></a>

Have you seen Barack Obama call Donald Trump a “[complete dipshit](https://www.youtube.com/watch?v=cQ54GDm1eL0\&feature=emb\_logo)”, or Mark Zuckerberg brag about having “[total control of billions of people’s stolen data](https://www.youtube.com/watch?v=Ox6L47Da0RY)”, or witnessed Jon Snow’s [moving apology](https://www.youtube.com/watch?v=4GdWD0yxvqw\&feature=emb\_logo) for the dismal ending to Game of Thrones? Answer yes and you’ve seen a deepfake. The 21st century’s answer to Photoshopping, deepfakes use a form of artificial intelligence called deep learning to make images of fake events, hence the name deepfake. Want to [put new words](https://www.youtube.com/watch?time\_continue=15\&v=yaq4sWFvnAY\&feature=emb\_logo) in a politician’s mouth, [star in your favourite movie](https://www.theguardian.com/technology/2019/sep/04/a-deep-fake-app-will-make-us-film-stars-but-will-we-regret-our-narcissism), or [dance like a pro](https://www.youtube.com/watch?v=PCBTZh41Ris\&feature=emb\_logo)? Then it’s time to make a deepfake.

### What are they for? <a href="#what-are-they-for" id="what-are-they-for"></a>

Many are pornographic. The AI firm Deeptrace found 15,000 deepfake videos online in September 2019, a near doubling over nine months. A staggering [96% were pornographic](https://deeptracelabs.com/mapping-the-deepfake-landscape/) and 99% of those mapped faces from female celebrities on to porn stars. As new techniques allow unskilled people to make deepfakes with a handful of photos, fake videos are likely to spread beyond the celebrity world to fuel revenge porn. As Danielle Citron, a professor of law at Boston University, puts it: “Deepfake technology is being weaponised against women.” Beyond the porn there’s plenty of spoof, satire and mischief.

### Is it just about videos? <a href="#is-it-just-about-videos" id="is-it-just-about-videos"></a>

No. Deepfake technology can create convincing but entirely fictional photos from scratch. A non-existent Bloomberg journalist, “Maisy Kinsley”, who had a profile on LinkedIn and Twitter, was probably a deepfake. Another LinkedIn fake, “Katie Jones”, claimed to work at the Center for Strategic and International Studies, but is thought to be a deepfake created for a foreign spying operation.

Audio can be deepfaked too, to create “[voice skins](https://modulate.ai/)” or ”[voice clones](https://www.respeecher.com/)” of public figures. Last March, the chief of a UK subsidiary of a German energy firm paid nearly £200,000 into a Hungarian bank account after being [phoned by a fraudster who mimicked the German CEO’s voice](https://www.wsj.com/articles/fraudsters-use-ai-to-mimic-ceos-voice-in-unusual-cybercrime-case-11567157402). The company’s insurers believe the voice was a deepfake, but the evidence is unclear. Similar scams have reportedly used recorded WhatsApp voice messages.

<figure><img src="https://i.guim.co.uk/img/media/61f857b39fd48a847fb1f8bce039710b536c4c2f/60_0_1800_1080/master/1800.jpg?width=445&#x26;quality=85&#x26;dpr=1&#x26;s=none" alt="A comparison of an original and deepfake video of Facebook chief executive Mark Zuckerberg."><figcaption><p>A comparison of an original and deepfake video of Facebook chief executive Mark Zuckerberg. Photograph: The Washington Post via Getty Images</p></figcaption></figure>

### How are they made? <a href="#how-are-they-made" id="how-are-they-made"></a>

University researchers and special effects studios have long pushed the boundaries of what’s possible with video and image manipulation. But deepfakes themselves were born in 2017 when a Reddit user of the same name posted doctored porn clips on the site. The videos swapped the faces of celebrities – Gal Gadot, Taylor Swift, Scarlett Johansson and others – on to porn performers.

It takes a few steps to make a face-swap video. First, you run thousands of face shots of the two people through an AI algorithm called an encoder. The encoder finds and learns similarities between the two faces, and reduces them to their shared common features, compressing the images in the process. A second AI algorithm called a decoder is then taught to recover the faces from the compressed images. Because the faces are different, you train one decoder to recover the first person’s face, and another decoder to recover the second person’s face. To perform the face swap, you simply feed encoded images into the “wrong” decoder. For example, a compressed image of person A’s face is fed into the decoder trained on person B. The decoder then reconstructs the face of person B with the expressions and orientation of face A. For a convincing video, this has to be done on every frame.

<figure><img src="https://i.guim.co.uk/img/media/14084b223de94e8bb98f982e39c35eeb46f7882a/0_0_5105_3062/master/5105.jpg?width=445&#x26;quality=85&#x26;dpr=1&#x26;s=none" alt="Original and deepfake videos of Vladimir Putin"><figcaption><p>Comparing original and deepfake videos of Russian president Vladimir Putin. Photograph: Alexandra Robinson/AFP via Getty Images</p></figcaption></figure>

Another way to make deepfakes uses what’s called a generative adversarial network, or Gan. A Gan pits two artificial intelligence algorithms against each other. The first algorithm, known as the generator, is fed random noise and turns it into an image. This synthetic image is then added to a stream of real images – of celebrities, say – that are fed into the second algorithm, known as the discriminator. At first, the synthetic images will look nothing like faces. But repeat the process countless times, with feedback on performance, and the discriminator and generator both improve. Given enough cycles and feedback, the generator will start producing [utterly realistic faces](https://research.nvidia.com/publication/2017-10\_Progressive-Growing-of) of completely nonexistent celebrities.

### Who is making deepfakes? <a href="#who-is-making-deepfakes" id="who-is-making-deepfakes"></a>

Everyone from academic and industrial researchers to amateur enthusiasts, visual effects studios and porn producers. Governments might be dabbling in the technology, too, as part of their [online strategies](https://theintercept.com/2015/06/22/controversial-gchq-unit-domestic-law-enforcement-propaganda/) to discredit and disrupt extremist groups, or [make contact](https://apnews.com/bc2f19097a4c4fffaa00de6770b8a60d) with targeted individuals, for example.

### What technology do you need? <a href="#what-technology-do-you-need" id="what-technology-do-you-need"></a>

It is hard to make a good deepfake on a standard computer. Most are created on high-end desktops with powerful graphics cards or better still with computing power in the cloud. This reduces the processing time from days and weeks to hours. But it takes expertise, too, not least to touch up completed videos to reduce flicker and other visual defects. That said, plenty of tools are now available to help people make deepfakes. Several companies will [make them for you](https://deepfakesweb.com/) and do all the processing in the cloud. There’s even a mobile phone app, [Zao](https://www.theguardian.com/technology/2019/sep/02/chinese-face-swap-app-zao-triggers-privacy-fears-viral), that lets users add their faces to a list of TV and movie characters on which the system has trained.

<figure><img src="https://i.guim.co.uk/img/media/1ce9be28462732664457fcf75d0a320f7a70c351/0_0_3456_2074/master/3456.jpg?width=445&#x26;quality=85&#x26;dpr=1&#x26;s=none" alt="Chinese face-swapping app Zao"><figcaption><p>Chinese face-swapping app Zao has caused privacy concerns. Photograph: Imaginechina/SIPA USA/PA Images</p></figcaption></figure>

### How do you spot a deepfake? <a href="#how-do-you-spot-a-deepfake" id="how-do-you-spot-a-deepfake"></a>

It gets harder as the technology improves. In 2018, [US researchers](https://arxiv.org/abs/1806.02877) discovered that deepfake faces don’t blink normally. No surprise there: the majority of images show people with their eyes open, so the algorithms never really learn about blinking. At first, it seemed like a silver bullet for the detection problem. But no sooner had the research been published, than deepfakes appeared with blinking. Such is the nature of the game: as soon as a weakness is revealed, it is fixed.

Poor-quality deepfakes are easier to spot. The lip synching might be bad, or the skin tone patchy. There can be flickering around the edges of transposed faces. And fine details, such as hair, are particularly hard for deepfakes to render well, especially where strands are visible on the fringe. Badly rendered jewellery and teeth can also be a giveaway, as can strange lighting effects, such as inconsistent illumination and reflections on the iris.

Governments, universities and tech firms are all funding research to detect deepfakes. Last month, the first [Deepfake Detection Challenge](https://deepfakedetectionchallenge.ai/) kicked off, backed by Microsoft, Facebook and Amazon. It will include research teams around the globe competing for supremacy in the deepfake detection game.

[Facebook last week banned deepfake videos that are likely to mislead viewers](https://www.theguardian.com/technology/2020/jan/07/facebook-bans-deepfake-videos-in-run-up-to-us-election) into thinking someone “said words that they did not actually say”, in the run-up to the 2020 US election. However, the policy covers only misinformation produced using AI, meaning “shallowfakes” (see below) are still allowed on the platform.

<figure><img src="https://i.guim.co.uk/img/media/99f253713f3cb1a945ea6129625e3141132762eb/0_0_3399_2040/master/3399.jpg?width=445&#x26;quality=85&#x26;dpr=1&#x26;s=none" alt="A woman watches a deepfake video of Donald Trump and Barack Obama."><figcaption><p>A woman watches a deepfake video of Donald Trump and Barack Obama. Photograph: Rob Lever/AFP via Getty Images</p></figcaption></figure>

### Will deepfakes wreak havoc? <a href="#will-deepfakes-wreak-havoc" id="will-deepfakes-wreak-havoc"></a>

We can expect more deepfakes that harass, intimidate, demean, undermine and destabilise. But will deepfakes spark major international incidents? Here the situation is less clear. A deepfake of a world leader pressing the big red button should not cause armageddon. Nor will deepfake satellite images of troops massing on a border cause much trouble: most nations have their own reliable security imaging systems.

There is still ample room for mischief-making, though. Last year, [Tesla stock crashed](https://www.theguardian.com/technology/2018/sep/07/tesla-chief-elon-musk-smokes-marijuana-on-live-web-show) when Elon Musk smoked a joint on a live web show. In December, Donald Trump flew home early from a Nato meeting when genuine [footage emerged](https://www.theguardian.com/us-news/2019/dec/04/footage-appears-to-show-world-leaders-joking-about-trump-at-nato-summit) of other world leaders apparently mocking him. Will plausible deepfakes shift stock prices, influence voters and provoke religious tension? It seems a safe bet.

### Will they undermine trust? <a href="#will-they-undermine-trust" id="will-they-undermine-trust"></a>

The more insidious impact of deepfakes, along with other synthetic media and fake news, is to create a zero-trust society, where people cannot, or no longer bother to, distinguish truth from falsehood. And when trust is eroded, it is easier to raise doubts about specific events.

Last year, Cameroon’s minister of communication dismissed as fake news a video that Amnesty International believes shows Cameroonianthe country’s [soldiers executing civilians](https://www.amnesty.org/en/latest/news/2018/09/digitally-dissecting-atrocities-amnesty-internationals-open-source-investigations/).

Donald Trump, who admitted to boasting about grabbing women’s genitals in a recorded conversation, later suggested [the tape was not real](https://www.theguardian.com/us-news/2017/nov/29/denying-accuracy-of-access-hollywood-tape-would-be-trumps-biggest-lie). In Prince Andrew’s BBC interview with Emily Maitlis, the prince [cast doubt on the authenticity of a photo](https://www.theguardian.com/uk-news/2019/sep/06/jeffrey-epstein-virginia-roberts-giuffre-prince-andrew-photo) taken with Virginia Giuffre, a shot her attorney insists is genuine and unaltered.

“The problem may not be so much the faked reality as the fact that real reality becomes plausibly deniable,” says Prof Lilian Edwards, a leading expert in internet law at Newcastle University.

As the technology becomes more accessible, deepfakes could mean trouble for the courts, particularly in child custody battles and employment tribunals, where faked events could be entered as evidence. But they also pose a personal security risk: deepfakes can mimic biometric data, and can potentially trick systems that rely on face, voice, vein or gait recognition. The potential for scams is clear. Phone someone out of the blue and they are unlikely to transfer money to an unknown bank account. But what if your “mother” or “sister” sets up a video call on WhatsApp and makes the same request?

### What’s the solution? <a href="#whats-the-solution" id="whats-the-solution"></a>

Ironically, AI may be the answer. Artificial intelligence already helps to spot fake videos, but many existing detection systems have a serious weakness: they work best for celebrities, because they can train on hours of freely available footage. Tech firms are now working on detection systems that aim to flag up fakes whenever they appear. Another strategy focuses on the provenance of the media. Digital watermarks are not foolproof, but a blockchain online ledger system could hold a tamper-proof record of videos, pictures and audio so their origins and any manipulations can always be checked.

### Are deepfakes always malicious? <a href="#are-deepfakes-always-malicious" id="are-deepfakes-always-malicious"></a>

Not at all. Many are entertaining and some are helpful. Voice-cloning deepfakes can [restore people’s voices](https://www.projectrevoice.org/) when they lose them to disease. Deepfake videos can enliven galleries and museums. In Florida, the Dalí museum has a deepfake of the surrealist painter who introduces his art and [takes selfies with visitors](https://www.youtube.com/watch?time\_continue=130\&v=BIDaxl4xqJ4\&feature=emb\_logo). For the entertainment industry, technology can be used to improve the dubbing on foreign-language films, and more controversially, resurrect dead actors. For example, the late James Dean is due to star in Finding Jack, a Vietnam war movie.

### What about shallowfakes? <a href="#what-about-shallowfakes" id="what-about-shallowfakes"></a>

Coined by Sam Gregory at the human rights organisation Witness, shallowfakes are videos that are either presented out of context or are doctored with simple editing tools. They are crude but undoubtedly impactful. A shallowfake video that slowed down Nancy Pelosi’s speech and made the US Speaker of the House sound slurred [reached millions of people](https://www.theguardian.com/technology/2019/may/24/facebook-leaves-fake-nancy-pelosi-video-on-site) on social media.

In another incident, Jim Acosta, a CNN correspondent, was temporarily banned from White House press briefings during a heated exchange with the president. A shallowfake video released afterwards appeared to show him making contact with an intern who tried to take the microphone off him. It later emerged that the video had been [sped up at the crucial moment](https://www.theguardian.com/media/2018/nov/19/jim-acosta-white-house-press-pass-trump-administration-suspend-letter), making the move look aggressive. Acosta’s press pass was later reinstated.

The UK’s Conservative party used similar shallowfake tactics. In the run-up to the recent election, the Conservatives [doctored a TV interview](https://www.theguardian.com/media/2019/nov/05/tories-unrepentant-about-doctored-video-of-keir-starmer-tv-appearance) with the Labour MP Keir Starmer to make it seem that he was unable to answer a question about the party’s Brexit stance. With deepfakes, the mischief-making is only likely to increase. As Henry Ajder, head of threat intelligence at Deeptrace, puts it: “The world is becoming increasingly more synthetic. This technology is not going away.”
