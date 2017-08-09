# Note_Android_Property

~~~Java
String androidId = Secure.getString(context.getContentResolver(), "android_id");
Build.BRAND
Build.DEVICE
Build.PRODUCT
MonitorMessages.SDK_VERSION
VERSION.SDK_INT
Build.MODEL
Build.TYPE
params.put("lang", Locale.getDefault().getDisplayLanguage());
params.put("lang_code", Locale.getDefault().getLanguage());
params.put("country", Locale.getDefault().getCountry());
TelephonyManager manager = (TelephonyManager) context.getSystemService("phone");
                params.put("operator", manager.getSimOperatorName());
                params.put("carrier", manager.getNetworkOperatorName());
~~~
