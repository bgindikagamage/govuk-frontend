# Warning text

## Introduction

Use bold text with an exclamation icon if there are consequences - for example, a fine or prison sentence.

## Guidance

Find out when to use the warning text component in your service in the [GOV.UK Design System](https://design-system.service.gov.uk/components/warning-text).

## Quick start examples

### Warning text

[Preview this example in the Frontend review app](http://govuk-frontend-review.herokuapp.com/components/warning-text/preview)

#### Markup

    <div class="govuk-warning-text">
      <span class="govuk-warning-text__icon" aria-hidden="true">!</span>
      <strong class="govuk-warning-text__text">
        <span class="govuk-warning-text__assistive">Warning</span>
        You can be fined up to £5,000 if you don’t register.
      </strong>
    </div>

#### Macro

    {% from "warning-text/macro.njk" import govukWarningText %}

    {{ govukWarningText({
      "text": "You can be fined up to £5,000 if you don’t register.",
      "iconFallbackText": "Warning"
    }) }}

## Requirements

### Build tool configuration

When compiling the Sass files you'll need to define includePaths to reference the node_modules directory. Below is a sample configuration using gulp

    .pipe(sass({
      includePaths: 'node_modules/'
    }))

### Static asset path configuration

In order to include the images used in the components, you need to configure your app to show these assets. Below is a sample configuration using Express js:

    app.use('/assets', express.static(path.join(__dirname, '/node_modules/govuk-frontend/assets')))

## Component arguments

If you are using Nunjucks,then macros take the following arguments

**If you’re using Nunjucks macros in production be aware that using `html` arguments, or ones ending with `Html` can be a [security risk](https://en.wikipedia.org/wiki/Cross-site_scripting). More about it in the [Nunjucks documentation](https://mozilla.github.io/nunjucks/api.html#user-defined-templates-warning).**

<table class="govuk-table">

<thead class="govuk-table__head">

<tr class="govuk-table__row">

<th class="govuk-table__header" scope="col">Name</th>

<th class="govuk-table__header" scope="col">Type</th>

<th class="govuk-table__header" scope="col">Required</th>

<th class="govuk-table__header" scope="col">Description</th>

</tr>

</thead>

<tbody class="govuk-table__body">

<tr class="govuk-table__row">

<th class="govuk-table__header" scope="row">text (or) html</th>

<td class="govuk-table__cell">string</td>

<td class="govuk-table__cell">Yes</td>

<td class="govuk-table__cell">Text or HTML for the warning text content. If `html` is provided, the `text` argument is ignored.</td>

</tr>

<tr class="govuk-table__row">

<th class="govuk-table__header" scope="row">iconFallbackText</th>

<td class="govuk-table__cell">string</td>

<td class="govuk-table__cell">Yes</td>

<td class="govuk-table__cell">The fallback text for the icon</td>

</tr>

<tr class="govuk-table__row">

<th class="govuk-table__header" scope="row">classes</th>

<td class="govuk-table__cell">string</td>

<td class="govuk-table__cell">No</td>

<td class="govuk-table__cell">Optional additional classes to add to the warning-text container.</td>

</tr>

<tr class="govuk-table__row">

<th class="govuk-table__header" scope="row">attributes</th>

<td class="govuk-table__cell">object</td>

<td class="govuk-table__cell">No</td>

<td class="govuk-table__cell">Any extra HTML attributes (for example data attributes) to add to the warning-text container.</td>

</tr>

</tbody>

</table>

**If you’re using Nunjucks macros in production be aware that using `html` arguments, or ones ending with `Html` can be a [security risk](https://en.wikipedia.org/wiki/Cross-site_scripting). More about it in the [Nunjucks documentation](https://mozilla.github.io/nunjucks/api.html#user-defined-templates-warning).**

### Setting up Nunjucks views and paths

Below is an example setup using express configure views:

    nunjucks.configure('node_modules/govuk-frontend/components', {
      autoescape: true,
      cache: false,
      express: app
    })

## Contribution

Guidelines can be found at [on our Github repository.](https://github.com/alphagov/govuk-frontend/blob/master/CONTRIBUTING.md "link to contributing guidelines on our github repository")

## License

MIT