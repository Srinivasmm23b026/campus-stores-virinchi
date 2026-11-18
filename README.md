# Campus Stores

I would keep Campus Stores and change the Friday-to-Saturday handover. The Loan register now lets the closing operator record who has an outstanding unit and when they expect it back, on the slip the opening operator will use to record the return.

## Run the app

Open `index.html` in a modern browser. The app runs offline with no installation or build step.

To serve it over local HTTP, run this from the repository folder and visit `http://localhost:8000`.

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Progress is saved in browser storage when available. Use **Restart sample shift** to restore the starting records.

## Where to find the change

Open **Loan register** and choose **Add handover** on an outstanding slip. Select the **Current holder** and **Expected return**, then choose **Save handover**. The details appear on that slip and can be edited until it is closed. [app.js](app.js) handles the slip display, form and saved data. [styles.css](styles.css) handles the layout at narrow widths. The candidate brief remains available in [index.html](index.html).

## One moment I would keep

At **Loan register → New issue slip**, I checked the projector choices before issuing PR-04 to Kabir. Inventory showed PR-06 in repair, and PR-06 was absent from the issue picker. I could issue the working projector without risking a slip for the unit in the workshop. I kept that availability rule.

## One moment I changed

At **Loan register → Outstanding** on Friday evening, I recorded returns for the projector and speaker. The adapter slip L-404 still showed Kabir and the original Friday due time. To pass on Leela's Saturday 9 a.m. plan, I switched to **Desk book → Add handover note** and typed the slip and asset IDs into the note. On Saturday I read the note and switched back to **Loan register** to match it to AD-12. The new handover fields put that information on L-404 while preserving the original collection record.

## Replay the same shift

| Shift | Before | With the prototype |
| --- | --- | --- |
| Fri 3:45 pm | Open RQ-214 in **Requests** to find the USB-C laptop note. Read Isha's pickup message in **Desk book**. Issue PR-04, SP-02 and AD-12 to Kabir Sen in **Loan register**, with the approved Friday 8 p.m. due time. | Issue the same three units, using one slip per unit. |
| Fri 7:30 pm | Use **Record return** on L-402 (PR-04) and L-403 (SP-02). Write the plan for L-404 and AD-12 in the Desk book. | Close the same two slips. On L-404, choose **Add handover**, select **Leela Das** and **Sat 9 am**, and save. |
| Sat 9:00 am | Read the note in the Desk book and find its asset and slip IDs in **Outstanding**. Match the adapter's physical label to AD-12 and close L-404. Leave the microphone slip L-401 open. | Open **Outstanding** and find **L-404 · AD-12** under Film Society with **With Leela Das · Expected Sat 9 am**. Match AD-12 to the physical label and close that slip. L-401 stays open. |

## Scope and trade-offs

I kept the approved requests, the one-slip-per-unit register, per-unit returns, the original collector and due time, and the free-text Desk book for general messages. The prototype records one current handover plan per slip using the sample's existing people and time choices. I left out custody history, reminders, and shared storage across devices.

## One observation at a real counter

Count how many times opening staff consult the Desk book to identify the outstanding unit during a partial-return handover. Compare that count per handover with and without the slip details.

## Verification and tools

I replayed both versions in Chrome. I checked that an older saved shift still opens, the handover form fits a narrow viewport, and the saved plan survives reopening the app. I returned AD-12, confirmed L-401 stayed open, and checked that **Restart sample shift** restored the starting records.

I used an AI assistant to inspect the app, prototype the change, verify the walkthrough, and draft this write-up.
