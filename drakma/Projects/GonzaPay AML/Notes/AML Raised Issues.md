---
project: GonzaPay AML
type: issues
---
# AML raised issues

## 🐞 Bug: AML-007 Dormant Account Activity fires wrongly
- **Rule:** a wallet with zero transactions in the past 90+ days suddenly sends more than 1,000,000 UGX (single-transaction, severity 10).
- **Problem:** it fires even when the wallet had transactions **days** before. Examples:
  - Alert 7 Sep for a 2,000,000 transfer on 2 Sep – "observed dormancy 150 days" – but the wallet had inbound transactions on 25–31 Aug.
  - Alert 28 Aug for a 1,770,000 transfer – "observed 142 days" – but the wallet had inbound transactions on 19–26 Aug.
- **Likely cause:** dormancy is measured from the last **outbound** transaction only, or inbound transactions aren't counted. Check how `dormancy_days` is calculated.
- [ ] Fix and re-test with the two cases above #aml

## Alerts and cases
- [ ] Dismiss an alert
- [ ] Assign an alert to a risk officer
- [ ] Risk officer opens a case from an alert
- [ ] Case management dashboard, notifications, case progression (26 Aug)
- [ ] Read-only user role
- Done: filters, inbound/outbound selection, bulk dismissal.

## Entity page layout
- [ ] Transaction volume chart: scroll horizontally instead of growing off the page or dropping below the risk profile.
- [ ] Risk profile box should fill the height so it lines up with the volume chart.
- [ ] Line chart: show the cumulative value at each point without hovering.
- [ ] Recent activity: last 10 only, with "View more".
- [ ] New section before recent activity: cases this entity is involved in (clean table, no heavy grid lines), filterable like transactions.
- [ ] Volume chart hover: a popover, not changing the header text. Add the "Hover a bar for details" hint to the risk profile too.

> Customer names in the examples below were removed from the original (data protection).

---

> [!note]- Original notes (unchanged)
> Alerts - Windows
> - Open/Closed 
>
>
> ### Remaining Issues
> - Alerts
> 	- dismiss
> 	- assign to risk officer
> 	- then risk officer can generate case for the alert, 
>
> - ~~add filters~~
> - ~~select by inbound/~~
> - ~~bulk selection of alerts - dismissal~~
> - User - with Read access
>
> 26-08-2026
> - dashboard - case management system
> - notifications
> - case progression
>
>
> - there is an issue; when transactions are very many, the transaction volume grows, best scenario it expands and now instead of being showed with the risk profile graph i t goes down, spanning the full page, but the issue is if its still large it grows past the page
> - desired would be it doesnt grow not only off the page, but also it doesnt go down, ie it is horizontally scrollable
> - then also vertically the risk profile container doesnt fill up the space so that its on the same level with the trnasaction volume compoent
> - then on the line, each point should show the cummulative value at that point even before hovering ie a number 
> - the recent activity section is showing a lot of transactions let it just show like the last 10, with action in the section view more on the right
> - then before recent activity, another section is added, which shows the cases that this person has been involved in, displayed neatly kinda like in table format. but no boring grid lines
> - you see the way transactions are filterable, cases should also be filterable, the filter ui for the transactions can be maintained
>
> - just like on risk profile, hovering the bar in transaction volume chart a pop over is to be displayed not changing text showed in the header
> - currrently there is a note on transaction volume ie "Hover a bar for details", this should also be included in the risk profile component
> - on the risk profile 
>
> - dormant account activity
> 	- it is not working as expected, it is flagging even when a customer has a previous transaction, transaction in space of not more than 90 days
> 	- |Date|Counterparty|Direction|Amount|
> |---|---|---|---|
> |Sep 2, 2026, 11:17 AM|[2510202297](https://aml.drakma.com/accounts/2510202297)|Outbound|10,000|
> |Sep 2, 2026, 11:14 AM|[2510202297](https://aml.drakma.com/accounts/2510202297)|Outbound|920,000|
> |Sep 2, 2026, 11:13 AM|[2510202297](https://aml.drakma.com/accounts/2510202297)|Outbound|2,000,000|
> |Sep 2, 2026, 11:12 AM|[2510202297](https://aml.drakma.com/accounts/2510202297)|Outbound|2,000,000|
> |Aug 31, 2026, 12:56 PM|[6981003](https://aml.drakma.com/accounts/6981003)|Inbound|650,000|
> |Aug 29, 2026, 04:58 PM|[6981001](https://aml.drakma.com/accounts/6981001)|Inbound|540,000|
> |Aug 29, 2026, 02:15 PM|[6981001](https://aml.drakma.com/accounts/6981001)|Inbound|1,520,000|
> |Aug 27, 2026, 06:19 PM|[6981003](https://aml.drakma.com/accounts/6981003)|Inbound|730,000|
> |Aug 25, 2026, 06:46 PM|[6981002](https://aml.drakma.com/accounts/6981002)|Inbound|1,490,000|
> |Apr 4, 2026, 10:10 PM|[772666184](https://aml.drakma.com/accounts/772666184)|Outbound|25,000|
>
> Dormant Account Activity
>
> A wallet with zero transactions in the past 90+ days suddenly initiates a transaction above 1,000,000 UGX.
>
> AssignOpen caseDismiss
>
> Severity
>
> 10
>
> Rule code
>
> AML-007
>
> Rule type
>
> Single transaction
>
> Detected
>
> Sep 7, 2026, 01:55 PM
>
> Why this fired
>
> - dormancy_days at least 90 — observed 150.542
>
> Triggering transaction
>
> View network graph
>
> |Reference|Date|Source|Destination|Amount|
> |---|---|---|---|---|
> |727805736908|Sep 2, 2026, 11:12 AM|WALLET[customer name removed](https://aml.drakma.com/accounts/WLT%40000048863)|BANK ACCOUNT[2510202297](https://aml.drakma.com/accounts/2510202297)|2,000,000|
>
> but check the triggering transaction, there are txns transacted even in august
>
>
> even it happened here
> |Date|Counterparty|Direction|Amount|
> |---|---|---|---|
> |Aug 28, 2026, 09:15 AM|[CRP@000099001](https://aml.drakma.com/accounts/CRP%40000099001)|Outbound|1,770,000|
> |Aug 26, 2026, 01:12 PM|[6983001](https://aml.drakma.com/accounts/6983001)|Inbound|30,000|
> |Aug 24, 2026, 08:43 AM|[6983001](https://aml.drakma.com/accounts/6983001)|Inbound|90,000|
> |Aug 19, 2026, 06:17 PM|[6983001](https://aml.drakma.com/accounts/6983001)|Inbound|1,650,000|
> |Apr 7, 2026, 07:13 PM|[3100094858](https://aml.drakma.com/accounts/3100094858)|Outbound|50,000|
> |Apr 3, 2026, 02:18 PM|[785148432](https://aml.drakma.com/accounts/785148432)|Outbound|52,000|
> |Mar 7, 2026, 10:52 PM|[3100003183](https://aml.drakma.com/accounts/3100003183)|Inbound|10,000|
>
>
> the entity txns one on 28th, even 26th, 
>
> Dormant Account Activity
>
> A wallet with zero transactions in the past 90+ days suddenly initiates a transaction above 1,000,000 UGX.
>
> AssignOpen caseDismiss
>
> Severity
>
> 10
>
> Rule code
>
> AML-007
>
> Rule type
>
> Single transaction
>
> Detected
>
> Aug 28, 2026, 09:03 AM
>
> Why this fired
>
> - dormancy_days at least 90 — observed 142.585
>
> Triggering transaction
>
> View network graph
>
> |Reference|Date|Source|Destination|Amount|
> |---|---|---|---|---|
> |737298685625|Aug 28, 2026, 09:15 AM|WALLET[customer name removed](https://aml.drakma.com/accounts/WLT%40000031251)|WALLET[Buy Ticket](https://aml.drakma.com/accounts/CRP%40000099001)|1,770,000|
> even it happens here the triggering txn, there are txns before that occurred before in shorter time frame
