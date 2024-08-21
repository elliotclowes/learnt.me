---
id: e80cb66f-1c44-4d23-a5ee-aaec913d4c6a
site_name: mccue.dev
date_saved: 2024-08-20
date_archived: 2024-08-20T16:11:15.000Z
original_url: https://mccue.dev/pages/8-16-24-just-use-postgres
omnivore_url: https://omnivore.app/me/just-use-postgres-191708e27f4
---

 - Site: mccue.dev
 - By: 
 - Date published: 
 - Date read: [[]]
 - [Read Original](https://mccue.dev/pages/8-16-24-just-use-postgres)
 - [Read on Omnivore](https://omnivore.app/me/just-use-postgres-191708e27f4)
 - Tags:  #Databases  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
<DIV id="readability-content"><DIV data-omnivore-anchor-idx="1" class="page" id="readability-page-1">

<p data-omnivore-anchor-idx="2"> by:  <b data-omnivore-anchor-idx="3"> Ethan McCue</b></p>

<p data-omnivore-anchor-idx="4">This is one part actionable advice, one part question for the audience.</p>
<p data-omnivore-anchor-idx="5">Advice: When you are making a new application that requires persistent storage of data, like is the case for most web applications, your default choice should be <code data-omnivore-anchor-idx="6" class="hljs language-ebnf"><span data-omnivore-anchor-idx="7" class="hljs-attribute">Postgres</span></code>.</p>
<h3 data-omnivore-anchor-idx="8" id="why-not-sqlite">Why not <code data-omnivore-anchor-idx="9" class="hljs language-ebnf"><span data-omnivore-anchor-idx="10" class="hljs-attribute">sqlite</span></code>?</h3>
<p data-omnivore-anchor-idx="11"><code data-omnivore-anchor-idx="12" class="hljs language-ebnf"><span data-omnivore-anchor-idx="13" class="hljs-attribute">sqlite</span></code> is a pretty good database, but its data is stored in a single file.</p>
<p data-omnivore-anchor-idx="14">This implies that whatever your application is, it is running on one machine and one machine only. Or at least one shared filesystem.</p>
<p data-omnivore-anchor-idx="15">If you are making a desktop or mobile app, that's perfect. If you are making a website it might not be.</p>
<p data-omnivore-anchor-idx="16">There are many success stories of using <code data-omnivore-anchor-idx="17" class="hljs language-ebnf"><span data-omnivore-anchor-idx="18" class="hljs-attribute">sqlite</span></code> for a website, but they mostly involve people who set up their own servers and infrastructure. Platforms as a service-s like Heroku, Railway, Render, etc. generally expect you to use a database accessed over network boundary. It's not <em data-omnivore-anchor-idx="19">wrong</em> to give up some of the benefits of those platforms, but do consider if the benefits of <code data-omnivore-anchor-idx="20" class="hljs language-ebnf"><span data-omnivore-anchor-idx="21" class="hljs-attribute">sqlite</span></code> are worth giving up platform provided automatic database backups and the ability to provision more than one application server.</p>
<p data-omnivore-anchor-idx="22"><a data-omnivore-anchor-idx="23" href="https://www.sqlite.org/whentouse.html">The official documentation</a> has a good guide with some more specifics.</p>
<h3 data-omnivore-anchor-idx="24" id="why-not-dynamodb-cassandra-or-mongodb">Why not <code data-omnivore-anchor-idx="25" class="hljs language-ebnf"><span data-omnivore-anchor-idx="26" class="hljs-attribute">DynamoDB</span></code>, <code data-omnivore-anchor-idx="27" class="hljs language-ebnf"><span data-omnivore-anchor-idx="28" class="hljs-attribute">Cassandra</span></code>, or <code data-omnivore-anchor-idx="29" class="hljs language-ebnf"><span data-omnivore-anchor-idx="30" class="hljs-attribute">MongoDB</span></code>?</h3>
<p data-omnivore-anchor-idx="31">Wherever Rick Houlihan is, I hope he is having a good day.</p>
<p data-omnivore-anchor-idx="32">I watch a lot of conference talks, but his <a data-omnivore-anchor-idx="33" href="https://www.youtube.com/watch?v=HaEPXoXVf2k">2018 DynamoDB Deep Dive</a> might be the one I've watched the most. I know very few of you are going to watch an hour-long talk, but you really should. It's a good one.</p>
<p data-omnivore-anchor-idx="34">The thrust of it is that databases that are in the same genre as <code data-omnivore-anchor-idx="35" class="hljs language-ebnf"><span data-omnivore-anchor-idx="36" class="hljs-attribute">DynamoDB</span></code> - which includes <code data-omnivore-anchor-idx="37" class="hljs language-ebnf"><span data-omnivore-anchor-idx="38" class="hljs-attribute">Cassandra</span></code> and <code data-omnivore-anchor-idx="39" class="hljs language-ebnf"><span data-omnivore-anchor-idx="40" class="hljs-attribute">MongoDB</span></code> - are fantastic <strong data-omnivore-anchor-idx="41">if</strong> - and this is a load bearing if:</p>
<ul data-omnivore-anchor-idx="42">
<li data-omnivore-anchor-idx="43">You know exactly what your app needs to do, up-front</li>
<li data-omnivore-anchor-idx="44">You know exactly what your access patterns will be, up-front</li>
<li data-omnivore-anchor-idx="45">You have a known need to scale to really large sizes of data</li>
<li data-omnivore-anchor-idx="46">You are okay giving up some level of consistency</li>
</ul>
<p data-omnivore-anchor-idx="47">This is because this sort of database is basically a giant distributed hash map. The only operations that work without needing to scan the entire database are lookups by partition key and scans that make use of a sort key.</p>
<p data-omnivore-anchor-idx="48">Whatever queries you need to make, you need to encode that knowledge in one of those indexes before you store it. You want to store users and look them up by either first name or last name? Well you best have a sort key that looks like <code data-omnivore-anchor-idx="49" class="hljs language-xml language-bnf"><span data-omnivore-anchor-idx="50" class="hljs-tag">&lt;<span data-omnivore-anchor-idx="51" class="hljs-name">FIRST</span> <span data-omnivore-anchor-idx="52" class="hljs-attr">NAME</span>&gt;</span>$<span data-omnivore-anchor-idx="53" class="hljs-tag">&lt;<span data-omnivore-anchor-idx="54" class="hljs-name">LAST</span> <span data-omnivore-anchor-idx="55" class="hljs-attr">NAME</span>&gt;</span></code>. Your access patterns should be baked into how you store your data. If your access patterns change significantly, you might need to reprocess all of your data.</p>
<p data-omnivore-anchor-idx="56">It's annoying because, especially with <code data-omnivore-anchor-idx="57" class="hljs language-ebnf"><span data-omnivore-anchor-idx="58" class="hljs-attribute">MongoDB</span></code>, people come into it having been sold on it being a more "flexible" database. Yes, you don't need to give it a schema. Yes, you can just dump untyped JSON into collections. No, this is not a flexible kind of database. It is an efficient one.</p>
<p data-omnivore-anchor-idx="59">With a relational database you can go from getting all the pets of a person to getting all the owners of a pet by slapping an index or two on your tables. With this genre of NoSQL, that can be a tall order.</p>
<p data-omnivore-anchor-idx="60">Its also not amazing if you need to run analytics queries. Arbitrary questions like "How many users signed up in the last month" can be trivially answered by writing a SQL query, perhaps on a read-replica if you are worried about running an expensive query on the same machine that is dealing with customer traffic. It's just outside the scope of this kind of database. You need to be ETL-ing your data out to handle it.</p>
<p data-omnivore-anchor-idx="61">If you see a college student or fresh grad using <code data-omnivore-anchor-idx="62" class="hljs language-ebnf"><span data-omnivore-anchor-idx="63" class="hljs-attribute">MongoDB</span></code> stop them. They need help. They have been led astray.</p>
<h3 data-omnivore-anchor-idx="64" id="why-not-valkey">Why not <code data-omnivore-anchor-idx="65" class="hljs language-ebnf"><span data-omnivore-anchor-idx="66" class="hljs-attribute">Valkey</span></code>?</h3>
<p data-omnivore-anchor-idx="67">The artist formerly known as <code data-omnivore-anchor-idx="68" class="hljs language-ebnf"><span data-omnivore-anchor-idx="69" class="hljs-attribute">Redis</span></code> is best known for being an efficient out-of-process cache. You compute something expensive once and slap it in <code data-omnivore-anchor-idx="70" class="hljs language-ebnf"><span data-omnivore-anchor-idx="71" class="hljs-attribute">Valkey</span></code> so all 5 or so HTTP servers you have don't need to recompute it.</p>
<p data-omnivore-anchor-idx="72">However, you <em data-omnivore-anchor-idx="73">can</em> use it as your primary database. It stores all its data in RAM, so it's pretty fast if you do that.</p>
<p data-omnivore-anchor-idx="74">Obvious problems:</p>
<ul data-omnivore-anchor-idx="75">
<li data-omnivore-anchor-idx="76">You can only have so much RAM. You can have a lot more than you'd think, but its still pretty limited compared to hard drives.</li>
<li data-omnivore-anchor-idx="77">Same as the <code data-omnivore-anchor-idx="78" class="hljs language-ebnf"><span data-omnivore-anchor-idx="79" class="hljs-attribute">DynamoDB</span></code>-likes, you need to make concessions on how you model your data.</li>
</ul>
<h3 data-omnivore-anchor-idx="80" id="why-not-datomic">Why not <code data-omnivore-anchor-idx="81" class="hljs language-ebnf"><span data-omnivore-anchor-idx="82" class="hljs-attribute">Datomic</span></code>?</h3>
<p data-omnivore-anchor-idx="83">If you already knew about this one, you get a gold star.</p>
<p data-omnivore-anchor-idx="84"><code data-omnivore-anchor-idx="85" class="hljs language-ebnf"><span data-omnivore-anchor-idx="86" class="hljs-attribute">Datomic</span></code> is a <code data-omnivore-anchor-idx="87" class="hljs language-ebnf"><span data-omnivore-anchor-idx="88" class="hljs-attribute">NoSQL</span></code> database, but it is a relational one. The "up-front design" problems aren't there, and it does have some neat properties.</p>
<p data-omnivore-anchor-idx="89">You don't store data in tables. It's all "entity-attribute-value-time" (EAVT) pairs. Instead of a person row with <code data-omnivore-anchor-idx="90" class="hljs language-applescript language-ebnf"><span data-omnivore-anchor-idx="91" class="hljs-built_in">id</span></code>, <code data-omnivore-anchor-idx="92" class="hljs language-applescript language-delphi"><span data-omnivore-anchor-idx="93" class="hljs-built_in">name</span></code>, and <code data-omnivore-anchor-idx="94" class="hljs language-ebnf"><span data-omnivore-anchor-idx="95" class="hljs-attribute">age</span></code> you store <code data-omnivore-anchor-idx="96" class="hljs language-basic language-elixir"><span data-omnivore-anchor-idx="97" class="hljs-symbol">1 </span>:person/<span data-omnivore-anchor-idx="98" class="hljs-keyword">name</span> <span data-omnivore-anchor-idx="99" class="hljs-string">"Beth"</span></code> and <code data-omnivore-anchor-idx="100" class="hljs language-basic language-elixir"><span data-omnivore-anchor-idx="101" class="hljs-symbol">1 </span>:person/age <span data-omnivore-anchor-idx="102" class="hljs-number">30</span></code>. Then your queries work off of "universal" indexes.</p>
<p data-omnivore-anchor-idx="103">You don't need to coordinate with writers when making queries. You query the database "as-of" a given time. New data, even deletions (or as they call them "retractions"), don't actually delete old data.</p>
<p data-omnivore-anchor-idx="104">But there are some significant problems</p>
<ul data-omnivore-anchor-idx="105">
<li data-omnivore-anchor-idx="106">It only works with JVM languages.</li>
<li data-omnivore-anchor-idx="107">Outside of <code data-omnivore-anchor-idx="108" class="hljs language-ebnf"><span data-omnivore-anchor-idx="109" class="hljs-attribute">Clojure</span></code>, a relatively niche language, its API sucks.</li>
<li data-omnivore-anchor-idx="110">If you structure a query badly the error messages you get are terrible.</li>
<li data-omnivore-anchor-idx="111">The whole universe of tools that exist for SQL just aren't there.</li>
</ul>
<h3 data-omnivore-anchor-idx="112" id="why-not-xtdb">Why not <code data-omnivore-anchor-idx="113" class="hljs language-ebnf"><span data-omnivore-anchor-idx="114" class="hljs-attribute">XTDB</span></code>?</h3>
<p data-omnivore-anchor-idx="115"><code data-omnivore-anchor-idx="116" class="hljs language-ebnf"><span data-omnivore-anchor-idx="117" class="hljs-attribute">Clojure</span></code> people make a lot of databases.</p>
<p data-omnivore-anchor-idx="118"><code data-omnivore-anchor-idx="119" class="hljs language-ebnf"><span data-omnivore-anchor-idx="120" class="hljs-attribute">XTDB</span></code> is spiritually similar do <code data-omnivore-anchor-idx="121" class="hljs language-ebnf"><span data-omnivore-anchor-idx="122" class="hljs-attribute">Datomic</span></code> but:</p>
<ul data-omnivore-anchor-idx="123">
<li data-omnivore-anchor-idx="124">There is an HTTP api, so you aren't locked to the JVM.</li>
<li data-omnivore-anchor-idx="125">It has two axes of time you can query against. "System Time" - when records were inserted - and "Valid Time."</li>
<li data-omnivore-anchor-idx="126">It has a SQL API.</li>
</ul>
<p data-omnivore-anchor-idx="127">The biggest points against it are:</p>
<ul data-omnivore-anchor-idx="128">
<li data-omnivore-anchor-idx="129">It's new. Its SQL API is something that popped up in the last year. It recently changed its whole storage model. Will the company behind it survive the next 10 years? Who knows!</li>
</ul>
<p data-omnivore-anchor-idx="130">Okay that's just one point. I'm sure I could think of more, but treat this as a stand-in for any recently developed database. The best predictor something will continue to exist into the future is how long it has existed. COBOL been around for decades, it will likely continue to exist for decades.</p>
<p data-omnivore-anchor-idx="131">If you have persistent storage, you want as long a support term as you can get. You can certainly choose to pick a newer or experimental database for your app but, regardless of technical properties, that's a risky choice. It shouldn't be your default.</p>
<h3 data-omnivore-anchor-idx="132" id="why-not-kafka">Why not <code data-omnivore-anchor-idx="133" class="hljs language-ebnf"><span data-omnivore-anchor-idx="134" class="hljs-attribute">Kafka</span></code>?</h3>
<p data-omnivore-anchor-idx="135"><code data-omnivore-anchor-idx="136" class="hljs language-ebnf"><span data-omnivore-anchor-idx="137" class="hljs-attribute">Kafka</span></code> is an append only log. It can handle TBs of data. It is a very good append only log. It works amazingly well if you want to do event sourcing type stuff with data flowing in from multiple services maintained by multiple teams of humans.</p>
<p data-omnivore-anchor-idx="138">But:</p>
<ul data-omnivore-anchor-idx="139">
<li data-omnivore-anchor-idx="140">Up to a certain scale, a table in Postgres works perfectly fine as an append only log.</li>
<li data-omnivore-anchor-idx="141">You likely do not have hundreds of people working on your product nor TBs of events flowing in.</li>
<li data-omnivore-anchor-idx="142">Making a Kafka consumer is a bit more error-prone than you'd expect. You need to keep track of your place in the log after all.</li>
<li data-omnivore-anchor-idx="143">Even when maintained by a cloud provider (and there are good managed <code data-omnivore-anchor-idx="144" class="hljs language-ebnf"><span data-omnivore-anchor-idx="145" class="hljs-attribute">Kafka</span></code> services) its another piece of infrastructure you need to monitor.</li>
</ul>
<h3 data-omnivore-anchor-idx="146" id="why-not-elasticsearch">Why not <code data-omnivore-anchor-idx="147" class="hljs language-ebnf"><span data-omnivore-anchor-idx="148" class="hljs-attribute">ElasticSearch</span></code>?</h3>
<p data-omnivore-anchor-idx="149">Is searching over data the primary function of your product?</p>
<p data-omnivore-anchor-idx="150">If yes, <code data-omnivore-anchor-idx="151" class="hljs language-ebnf"><span data-omnivore-anchor-idx="152" class="hljs-attribute">ElasticSearch</span></code> is going to give you some real pros. You will need to ETL your data into it and manage that whole process, but <code data-omnivore-anchor-idx="153" class="hljs language-ebnf"><span data-omnivore-anchor-idx="154" class="hljs-attribute">ElasticSearch</span></code> is built for searching. It does searching good.</p>
<p data-omnivore-anchor-idx="155">If no, <code data-omnivore-anchor-idx="156" class="hljs language-ebnf"><span data-omnivore-anchor-idx="157" class="hljs-attribute">Postgres</span></code> will be fine. A sprinkling of <code data-omnivore-anchor-idx="158" class="hljs language-ebnf language-pgsql"><span data-omnivore-anchor-idx="159" class="hljs-attribute">ilike</span></code> and the built-in <a data-omnivore-anchor-idx="160" href="https://www.postgresql.org/docs/current/textsearch.html">full text search</a> is more than enough for most applications. You can always bolt on a dedicated search thing later.</p>
<h3 data-omnivore-anchor-idx="161" id="why-not-mssql-or-oracle-db">Why not <code data-omnivore-anchor-idx="162" class="hljs language-ebnf"><span data-omnivore-anchor-idx="163" class="hljs-attribute">MSSQL</span></code> or <code data-omnivore-anchor-idx="164" class="hljs language-ebnf language-excel"><span data-omnivore-anchor-idx="165" class="hljs-attribute">Oracle DB</span></code>?</h3>
<p data-omnivore-anchor-idx="166">Genuine question you should ask yourself: Are these worth the price tag?</p>
<p data-omnivore-anchor-idx="167">I don't just mean the straight-up cost to license, but also the cost of lock-in. Once your data is in <code data-omnivore-anchor-idx="168" class="hljs language-ebnf language-excel"><span data-omnivore-anchor-idx="169" class="hljs-attribute">Oracle DB</span></code> you are going to be paying Oracle forever. You are going to have to train your coders on its idiosyncrasies, forever. You are going to have to decide between enterprise features and your wallet, forever.</p>
<p data-omnivore-anchor-idx="170">I know its super unlikely that you will contribute a patch to <code data-omnivore-anchor-idx="171" class="hljs language-ebnf"><span data-omnivore-anchor-idx="172" class="hljs-attribute">Postgres</span></code>, so I won't pretend that there is some magic "power of open source" going on, but I think you should have a very specific need in mind to choose a proprietary DB. If you don't have some killer <code data-omnivore-anchor-idx="173" class="hljs language-ebnf"><span data-omnivore-anchor-idx="174" class="hljs-attribute">MSSQL</span></code> feature that you simply cannot live without, don't use it.</p>
<h3 data-omnivore-anchor-idx="175" id="why-not-mysql">Why not <code data-omnivore-anchor-idx="176" class="hljs language-ebnf"><span data-omnivore-anchor-idx="177" class="hljs-attribute">MySQL</span></code>?</h3>
<p data-omnivore-anchor-idx="178">This is the one that I need some audience help with.</p>
<p data-omnivore-anchor-idx="179"><code data-omnivore-anchor-idx="180" class="hljs language-ebnf"><span data-omnivore-anchor-idx="181" class="hljs-attribute">MySQL</span></code> is owned by Oracle. There are <a data-omnivore-anchor-idx="182" href="https://www.mysql.com/products/enterprise/compare/">features locked behind their enterprise editions</a>. To an extent you will have lock-in issues the same as any other DB.</p>
<p data-omnivore-anchor-idx="183">But the free edition <code data-omnivore-anchor-idx="184" class="hljs language-ebnf"><span data-omnivore-anchor-idx="185" class="hljs-attribute">MySQL</span></code> has also been used in an extremely wide range of things. It's been around for a long time. There are people who know how to work with it.</p>
<p data-omnivore-anchor-idx="186">My problem is that I've only spent ~6 months of my professional career working with it. I genuinely don't know enough to compare it intelligently to <code data-omnivore-anchor-idx="187" class="hljs language-ebnf"><span data-omnivore-anchor-idx="188" class="hljs-attribute">Postgres</span></code>.</p>
<p data-omnivore-anchor-idx="189">I'm convinced it isn't secretly so much better that I am doing folks a disservice when telling them to use <code data-omnivore-anchor-idx="190" class="hljs language-ebnf"><span data-omnivore-anchor-idx="191" class="hljs-attribute">Postgres</span></code>, and I do remember reading about how <code data-omnivore-anchor-idx="192" class="hljs language-ebnf"><span data-omnivore-anchor-idx="193" class="hljs-attribute">Postgres</span></code> generally has better support for enforcing invariants in the DB itself, but I wouldn't mind being schooled a bit here.</p>
<h3 data-omnivore-anchor-idx="194" id="why-not-some-ai-vector-db">Why not some AI vector DB?</h3>
<ul data-omnivore-anchor-idx="195">
<li data-omnivore-anchor-idx="196">Most are new. Remember the risks of using something new.</li>
<li data-omnivore-anchor-idx="197">AI is a bubble. A load-bearing bubble, but a bubble. Don't build a house on it if you can avoid it.</li>
<li data-omnivore-anchor-idx="198">Even if your business is another AI grift, you probably only need to <code data-omnivore-anchor-idx="199" class="hljs language-elm language-haskell"><span data-omnivore-anchor-idx="200" class="hljs-keyword">import</span> openai</code>.</li>
</ul>
<h3 data-omnivore-anchor-idx="201" id="why-not-google-sheets">Why not Google Sheets?</h3>
<p data-omnivore-anchor-idx="202">You're right. I can't think of any downsides. Go for it.</p>
<hr data-omnivore-anchor-idx="203">
<h4 data-omnivore-anchor-idx="204" id="--index"><a data-omnivore-anchor-idx="205" href="https://mccue.dev/">&lt;- Index</a></h4>
</DIV></DIV>