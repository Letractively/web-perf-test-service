import java.io.IOException;
import java.net.MalformedURLException;

import javax.xml.namespace.QName;
import javax.xml.rpc.ServiceException;

import org.apache.axis.client.Call;
import org.apache.axis.client.Service;
import org.apache.commons.logging.Log;
import org.apache.commons.logging.LogFactory;

public class PDSTest {
> private static final Log log = LogFactory.getLog(PDSTest.class);
> private static final String WEB\_PERF\_SERVICE\_ENDPOINT = "http://172.0.0.1:8086/WPS/services/PDS?wsdl";

> /
    * Call HttpWatchService to collect web perf data by operating Selenium 2.0.
    * 
> public void callHWS() {
> > try {
> > > Service service = new Service();
> > > Call call = (Call) service.createCall();
> > > call.setTargetEndpointAddress(new java.net.URL(WEB\_PERF\_SERVICE\_ENDPOINT));
> > > call.setOperationName(new QName("http://sc-node-core/", "callHWS"));
> > > call.addParameter("url", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.addParameter("browser", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.addParameter("needClearCache", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.addParameter("harFileName", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.setReturnType(org.apache.axis.Constants.XSD\_STRING);
> > > try {
> > > > String ret = (String) call.invoke(new Object[.md](.md) { "http://www.google.com", "ie6", "true", "testGoogleHomePage" });
> > > > System.out.println("The return value is:" + ret);
> > > > return;

> > > } catch (IOException e) {
> > > > e.printStackTrace();

> > > }

> > } catch (MalformedURLException e) {
> > > e.printStackTrace();

> > } catch (ServiceException e) {
> > > e.printStackTrace();

> > }

> }

> /
    * Call BrowserMobProxyService to collect web perf data by operating
    * Selenium 2.0.
    * 
> public void callBMPS() {
> > try {
> > > Service service = new Service();
> > > Call call = (Call) service.createCall();
> > > call.setTargetEndpointAddress(new java.net.URL(WEB\_PERF\_SERVICE\_ENDPOINT));
> > > call.setOperationName(new QName("http://sc-node-core/", "callBMPS"));
> > > call.addParameter("url", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.addParameter("browser", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.addParameter("needClearCache", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.addParameter("harFileName", org.apache.axis.Constants.XSD\_STRING, javax.xml.rpc.ParameterMode.IN);
> > > call.setReturnType(org.apache.axis.Constants.XSD\_STRING);
> > > try {
> > > > String ret = (String) call.invoke(new Object[.md](.md) { "http://www.google.com", "ie6", "true", "testGoogleHomePage" });
> > > > System.out.println("The return value is:" + ret);
> > > > return;

> > > } catch (IOException e) {
> > > > e.printStackTrace();

> > > }

> > } catch (MalformedURLException e) {
> > > e.printStackTrace();

> > } catch (ServiceException e) {
> > > e.printStackTrace();

> > }

> }

> public static void main(String[.md](.md) args) {
> > PDSTest tester = new PDSTest();
> > tester.callHWS();
> > tester.callBMPS();

> }
}