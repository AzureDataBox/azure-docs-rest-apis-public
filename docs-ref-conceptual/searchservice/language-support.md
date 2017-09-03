---
title: "Language analyzers (Azure Search Service REST API)"
ms.custom: ""
ms.date: "2017-09-02"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "search"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: 8f35915a-2bfa-4f23-80c3-e3f54e9e4543
caps.latest.revision: 28
author: "Yahnoosh"
ms.author: "jlembicz"
manager: "pablocas"
translation.priority.mt:
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pt-br"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
---
# Language analyzers (Azure Search Service REST API)

A *language analyzer* is a specific component of a [full-text search engine](https://docs.microsoft.com/azure/search/search-lucene-query-architecture) that performs lexical analysis using the linguistic rules of the target language. You can specify which analyzer to use on a field-by-field basis. 

By default, searchable fields in Azure Search are analyzed with the [Apache Lucene Standard analyzer (standard lucene)](http://lucene.apache.org/core/4_9_0/analyzers-common/index.html) which breaks text into elements following the ["Unicode Text Segmentation"](http://unicode.org/reports/tr29/) rules. Additionally, the standard analyzer converts all characters to their lower case form. Both indexed documents and search terms go through the analysis during indexing and query processing.    

Azure Search provides text analyzers that account for characteristics of various languages. You can choose from Lucene and Microsoft analyzers:

-   35 analyzers backed by Lucene.  

-   50 analyzers backed by proprietary Microsoft natural language processing technology used in Office and Bing.  

 Some developers might prefer the more familiar, simple, open-source solution of Lucene. Lucene language analyzers are faster, but the Microsoft analyzers have advanced capabilities, such as lemmatization, word decompounding (in languages like German, Danish, Dutch, Swedish, Norwegian, Estonian, Finish, Hungarian, Slovak) and entity recognition (URLs, emails, dates, numbers). If possible, you should run comparisons of both the Microsoft and Lucene analyzers to decide which one is a better fit.  

## Compare analyzer types 

 The Lucene analyzer for English extends the standard analyzer. It removes possessives (trailing 's) from words, applies stemming as per Porter Stemming algorithm, and removes English stop words.  

 In comparison, the Microsoft analyzer performs lemmatization instead of stemming. This means it can handle inflected and irregular word forms much better what results in more relevant search results

 Indexing with Microsoft analyzers is on average two to three times slower than their Lucene equivalents, depending on the language. Search performance should not be significantly affected for average size queries.  

 > [!Tip]
 > The [Search Analyzer Demo](http://alice.unearth.ai/) provides side-by-side comparison of results produced by the standard Lucene analyzer, Lucene's English language analyzer, and Microsoft's English natural language processor. For each search input you provide, results from each analyzer are displayed in adjacent panes.

## Analyzer configuration

 For each field in the index definition, you can set the analyzer property to an analyzer name that specifies which language and vendor. The same analyzer will be applied when indexing and searching for that field. For example, you can have separate fields for English, French, and Spanish hotel descriptions that exist side-by-side in the same index.  

 Use the **searchFields** query parameter to specify which language-specific field to search against in your queries. You can review query examples that include the analyzer property in Search Documents.  
Analyzer list  
Below is the list of supported languages together with Lucene and Microsoft analyzer names.  
See [Create Index &#40;Azure Search Service REST API&#41;](create-index.md) for details on how to specify the language analyzer on a field in the index.  

> [!IMPORTANT]  
>  Support for Microsoft's natural language processors via the REST API in Azure Search is now out of preview and in the generally available release. Additionally, both Lucene analyzers and Microsoft's natural language  processors are available in the Azure Search .NET library.  

## Analyzer List  
 Below is the list of supported languages together with Lucene and Microsoft analyzer names.  

|Language|Microsoft Analyzer Name|Lucene Analyzer Name|  
|--------------|-----------------------------|--------------------------|  
|Arabic|ar.microsoft|ar.lucene|  
|Armenian||hy.lucene|  
|Bangla|bn.microsoft||  
|Basque||eu.lucene|  
|Bulgarian|bg.microsoft|bg.lucene|  
|Catalan|ca.microsoft|ca.lucene|  
|Chinese Simplified|zh-Hans.microsoft|zh-Hans.lucene|  
|Chinese Traditional|zh-Hant.microsoft|zh-Hant.lucene|  
|Croatian|hr.microsoft||  
|Czech|cs.microsoft|cs.lucene|  
|Danish|da.microsoft|da.lucene|  
|Dutch|nl.microsoft|nl.lucene|  
|English|en.microsoft|en.lucene|  
|Estonian|et.microsoft||  
|Finnish|fi.microsoft|fi.lucene|  
|French|fr.microsoft|fr.lucene|  
|Galician||gl.lucene|  
|German|de.microsoft|de.lucene|  
|Greek|el.microsoft|el.lucene|  
|Gujarati|gu.microsoft||  
|Hebrew|he.microsoft||  
|Hindi|hi.microsoft|hi.lucene|  
|Hungarian|hu.microsoft|hu.lucene|  
|Icelandic|is.microsoft||  
|Indonesian (Bahasa)|id.microsoft|id.lucene|  
|Irish||ga.lucene|  
|Italian|it.microsoft|it.lucene|  
|Japanese|ja.microsoft|ja.lucene|  
|Kannada|ka.microsoft||  
|Korean|ko.microsoft|ko.lucene|  
|Latvian|lv.microsoft|lv.lucene|  
|Lithuanian|lt.microsoft||  
|Malayalam|ml.microsoft||  
|Malay (Latin)|ms.microsoft||  
|Marathi|mr.microsoft||  
|Norwegian|nb.microsoft|no.lucene|  
|Persian||fa.lucene|  
|Polish|pl.microsoft|pl.lucene|  
|Portuguese (Brazil)|pt-Br.microsoft|pt-Br.lucene|  
|Portuguese (Portugal)|pt-Pt.microsoft|pt-Pt.lucene|  
|Punjabi|pa.microsoft||  
|Romanian|ro.microsoft|ro.lucene|  
|Russian|ru.microsoft|ru.lucene|  
|Serbian (Cyrillic)|sr-cyrillic.microsoft||  
|Serbian (Latin)|sr-latin.microsoft||  
|Slovak|sk.microsoft||  
|Slovenian|sl.microsoft||  
|Spanish|es.microsoft|es.lucene|  
|Swedish|sv.microsoft|sv.lucene|  
|Tamil|ta.microsoft||  
|Telugu|te.microsoft||  
|Thai|th.microsoft|th.lucene|  
|Turkish|tr.microsoft|tr.lucene|  
|Ukrainian|uk.microsoft||  
|Urdu|ur.microsoft||  
|Vietnamese|vi.microsoft||  

 Additionally Azure Search provides language-agnostic analyzer configurations:  

||||  
|-|-|-|  
|Standard ASCII Folding|standardasciifolding.lucene|-   Unicode text segmentation (Standard Tokenizer)<br />-   ASCII folding filter - converts Unicode characters that don't belong to the set of first 127 ASCII characters into their ASCII equivalents. This is useful for removing diacritics|  

 All analyzers with names annotated with **Lucene** are powered by [Apache Lucene's language analyzers](http://lucene.apache.org/core/4_9_0/analyzers-common/overview-summary.html). More information about the ASCII folding filter can be found [Class ASCIIFoldingFilter](http://lucene.apache.org/core/4_9_0/analyzers-common/org/apache/lucene/analysis/miscellaneous/ASCIIFoldingFilter.html).  

## See also  
 [Create Index &#40;Azure Search Service REST API&#41;](create-index.md)  
 [AnalyzerName Class](https://docs.microsoft.com/dotnet/api/microsoft.azure.search.models.analyzername)  
 [Video: module 7 of Azure Search MVA presentation](https://channel9.msdn.com/Series/Adding-Microsoft-Azure-Search-to-Your-Websites-and-Apps/07).  

