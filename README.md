# Biztalk Server 2010 Pipeline Component XslMappingComponent

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://github.com/neozhu)

In the biztalk receive pipeline / send pipeline  process source message mapping output

# New Features!

  - According to the specified xsl document  transform  output the message



 

### Tech

 Code:

            XslCompiledTransform xsl = new XslCompiledTransform();
            XsltSettings setting = new XsltSettings(true, true);
            setting.EnableDocumentFunction = true;
            setting.EnableScript = true;
          
            var outStream = new MemoryStream();
            xslReader.MoveToFirstAttribute();
            xsl.Load(XmlReader.Create(this.XslPath), setting, null);
            inStream.Seek(0, SeekOrigin.Begin);
            xsl.Transform(XmlReader.Create(inStream), null, outStream);
            outStream.Seek(0, SeekOrigin.Begin);
            return outStream;

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

 
