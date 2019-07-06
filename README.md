## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/anuprath87/anuprath87.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

package javasamples.one;

import javax.xml.namespace.QName;
import javax.xml.ws.Service;
import java.net.URL;

class TimeClient {

    public static void main(String args[ ]) throws Exception {

        URL url = new URL("http://localhost:1111/one?wsdl");

        // Qualified name of the service:
        //   1st arg is the service URI
        //   2nd is the service name published in the WSDL

        QName qname = new QName("http://one.javasamples/", "TimeServerImplService");

        // Create, in effect, a factory for the service.

        Service service = Service.create(url, qname);

        // Extract the endpoint interface, the service "port".

        TimeServer eif = service.getPort(TimeServer.class);

        System.out.println(eif.getTimeAsString());
        System.out.println(eif.getTimeAsElapsed());

   }

}


### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/anuprath87/anuprath87.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
