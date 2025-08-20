
# Content Creation with AI


## Prompting

> Prompting is the process of designing and refining input queries to AI models to achieve desired outputs. It involves crafting specific instructions or questions that guide the AI in generating relevant and accurate responses.

    {{1}}
<section>

## 5 Step Framework (by Google)

1. __Task:__ What the AI shall do!
2. __Context:__ Background information and details relevant to the task.
3. __References:__ Any external sources or materials to consider.
4. __Evaluate:__ Criteria for assessing the output.
5. __Iterate:__ Process for refining the prompt based on feedback.

</section>

### 1. Task

__What the AI shall do!__

``` markdown
Make suggestions for a poetry course for 2nd graders.
```

    {{1}}
<section>

#### Persona

__Instead of only focusing on the task, instruct the AI to have a certain background.__

``` markdown
You are a teacher and a hobby poet that loves to inspire young minds.
Make suggestions for a poetry course for 2nd graders.
```

</section>

    {{2}}
<section>

#### Format

__Give detailed instructions on how the output should be structured and formatted and define upper bounds.__

``` markdown
You are a teacher and a hobby poet that loves to inspire young minds.
Make suggestions for a poetry course for 2nd graders.
Format the output as a table of 5 topics.
```

</section>


### 2. Context

The more context you can provide the better the AI can understand the task and generate relevant outputs. Consider including:

- Specific details about the target audience (e.g., age, background, interests, abilities, ...)
- Any constraints or limitations (e.g., word count, style guidelines)


    {{1}}
``` markdown
You are a teacher and a hobby poet that loves to inspire young minds.
Make suggestions for a poetry course for 2nd graders.

- The students have a basic understanding of language.
- Students come from diverse cultural backgrounds.
- Some of them are not fluent in English.
```

### 3. References

References are any external sources or materials that can provide additional context or information relevant to the task.

The AI is very very very good in using examples. So if you already have some specific material that you like, probably for another target group, you can share that as well.

    {{1}}
``` markdown
You are a teacher and a hobby poet that loves to inspire young minds.
Make suggestions for a poetry course for 2nd graders.

- The students have a basic understanding of language.
- Students come from diverse cultural backgrounds.
- Some of them are not fluent in English.

----

In Germany we have a poem format called "Elfchen" (Elevenie).

It consists of 11 words arranged in a specific pattern:

1. One word (the title)
2. Two words (describing the title)
3. Three words (expressing a feeling about the title)
4. Four words (describing a scene related to the title)
5. One word (a synonym for the title)

This format can be a simple starting point, encourages creativity
and helps young poets focus on specific aspects of their subject.
```

### 4. Evaluate & 5. Iterate

    {{1}}
__Is this the output that I wanted?__

    {{2}}
__If not, what can be improved? How can I refine the prompt to get closer to the desired output?__

## Technologies

https://ai-27.com

### Libraries

- [AI for Education](https://www.aiforeducation.io/prompt-library)

- [Microsoft Prompts for Education](https://github.com/microsoft/prompts-for-edu)

- [UNIGlobal Careers Prompt Library](https://learn.uniglobalcareers.com/docs/prompt-library/)

### Tools

    {{1-2}}
??[ai-27](https://ai-27.com)


    {{2}}
??[Prompt-Library](https://aipromptlibrary.org/library.html)

## Prompting Techniques

### Variables & Templates

`[ Variables ]` are placeholders that can be used to represent different values in a prompt.

Later these variables can be replaced with specific values when the prompt is executed. (`variable == new value`)

    {{1}}
``` markdown                 visualization
The following LiaScript code generates an interactive chart on different types of quadratic functions,
where the user can manipulate certain parameters.
Rewrite this to draw another [ visualization ] and change the number of input parameters, if required.
Mark this prompt as "UNDERSTOOD" when you are ready and wait for further instructions.

$a =$ <script modify="false" input="range" step="1"   min="-1"  max="6"  value="2" output="a">@input</script>,
$b =$ <script modify="false" input="range" step="0.1" min="-10" max="10" value="0" output="b">@input</script>,
$c =$ <script modify="false" input="range" step="0.1" min="-10" max="10" value="0" output="c">@input</script>

<script modify="false" run-once style="display: inline-block; width: 100%">
"LIASCRIPT: ### $$f(x) = x^{@input(`a`)} + x * @input(`b`) + @input(`c`)$$"
</script>

<script run-once style="display: inline-block; width: 100%">
function func(x) {
  return Math.pow(x,  @input(`a`)) + @input(`b`) * x + @input(`c`);
}

function generateData() {
  let data = [];
  for (let i = -15; i <= 15; i += 0.01) {
    data.push([i, func(i)]);
  }
  return data;
}

let option = {
  grid: { top: 40, left: 50, right: 40, bottom: 50 },
  xAxis: {
    name: 'x',
    minorTick: { show: true },
    splitLine: { lineStyle: { color: '#999' } },
    minorSplitLine: { show: true, lineStyle: { color: '#ddd' } }
  },
  yAxis: {
    name: 'y', min: -10, max: 10,
    minorTick: { show: true },
    splitLine: { lineStyle: { color: '#999' } },
    minorSplitLine: { show: true, lineStyle: { color: '#ddd' } }
  },
  series: [
    {
      type: 'line',
      showSymbol: false,
      data: generateData()
    }
  ]
};

"HTML: <lia-chart option='" + JSON.stringify(option) + "'></lia-chart>"
</script>
```

### Chain of Thought (CoT)

### Tree of Thought (ToT)

### Output Formats

https://github.com/liascript/markdownify

https://liascript.github.io/Markdownify/

## Video generation


## AI Workflows

## Opal-Apps