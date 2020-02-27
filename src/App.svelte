<script>
  import HTTPCode from "./HTTPCode.svelte";

  const Code = (code, title, desc = "") => ({
    code,
    title,
    desc,
    image: `/images/Code-${code}.jpg`
  });
  const codes = [
    Code(
      301,
      "Moved Permanently",
      "This and all future requests should be directed to the given URI"
    ),
    Code(302, "Found", 'Previously "Moved temporarily"'),
    Code(
      305,
      "Use Proxy",
      "The requested resource is available only through a proxy)"
    ),
    Code(
      307,
      "Temporary Redirect",
      "The request should be repeated with another URI; however, future requests should still use the original URI."
    ),
    Code(
      400,
      "Bad Request",
      "The server cannot or will not process the request due to an apparent client error."
    ),
    Code(402, "Payment Required"),
    Code(
      403,
      "Forbidden",
      "The request contained valid data and was understood by the server, but the server is refusing action."
    ),
    Code(
      404,
      "Not Found",
      "The requested resource could not be found but may be available in the future. Subsequent requests by the client are permissible."
    ),
    Code(
      406,
      "Not Acceptable",
      "The requested resource is capable of generating only content not acceptable according to the Accept headers sent in the request."
    ),
    Code(
      408,
      "Request Timeout",
      "The server timed out waiting for the request."
    ),
    Code(
      409,
      "Conflict",
      "The request could not be processed because of conflict in the current state of the resource."
    ),
    Code(
      410,
      "Gone",
      "The resource requested is no longer available and will not be available again."
    ),
    Code(
      413,
      "Payload Too Large",
      "The request is larger than the server is willing or able to process."
    ),
    Code(
      417,
      "Expectation Failed",
      "The server cannot meet the requirements of the Expect request-header field."
    ),
    Code(418, "I'm a teapot", "April Fools' joke"),
    Code(
      420,
      "Policy Not Fulfilled",
      "Enhance Your Calm (Twitter) - Method Failure (Spring Framework)"
    ),
    Code(
      422,
      "Unprocessable Entity",
      "The request was well-formed but was unable to be followed due to semantic errors."
    ),
    Code(500, "Internal Server Error", "Generic error message")
  ];
</script>

<style>
  main {
    text-align: center;
    margin: 0 auto;
    max-width: 1200px;
    color: #292f36;
    padding: 1rem;
  }

  h1 {
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  a,
  a:visited {
    color: #ff6b6b;
  }

  .codes {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
</style>

<main>
  <h1>HTTP Error Codes</h1>
  <p>
    <a
      href="https://en.m.wikipedia.org/wiki/List_of_HTTP_status_codes"
      target="_blank">
      HTTP Codes - Wikipedia
    </a>
  </p>
  <p>
    Idea by u/ryuexeu (
    <a
      href="https://www.reddit.com/r/ProgrammerHumor/comments/fa8cbq/http_errors_irl/"
      target="_blank">
      Reddit Thread
    </a>
    )
  </p>
  <p>
    404 Author not found - If you know/are the author of these illustrations,
    please send me a DM on reddit (
    <a href="https://www.reddit.com/u/alfiegoldson" target="_blank">
      u/AlfieGoldson
    </a>
    ) so I can properly give credit.
  </p>
  <div class="codes">
    {#each codes as code}
      <HTTPCode {...code} />
    {/each}
  </div>

</main>
