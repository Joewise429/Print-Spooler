# Print-Spooler
# Print Spooler

An interactive web page that simulates a shared office printer using a queue. Print jobs wait in a first-in, first-out (FIFO) line and print in the order they were submitted.

It was built for an assignment on real-world applications of queues. The print spooler is the chosen application.

## Why a queue

Many users send documents to one printer. The printer handles one job at a time and is much slower than the users. A queue holds the waiting jobs so that:

- jobs are printed fairly, in arrival order
- nothing is lost while the printer is busy
- users do not have to wait for the printer before continuing their work

## Features

- **Submit a job** with a user name, document name and page count
- **Print next** to send the front job to the printer
- **Print automatically** to keep the printer working until the queue is empty
- **Speed control** (slow, normal, fast) for the page-by-page printing
- **Cancel** any waiting job
- **Simulate a paper jam**, which puts the current job back at the rear of the queue
- **Live totals** for jobs waiting, jobs printed, pages printed and jobs cancelled
- **Activity log** of every queue and printer event

The page opens with three example jobs (Ama, Kofi and Esi) so you can try it straight away.

## Run it

No install or build step is needed.

1. Save `print-spooler.html` to your computer.
2. Open it in any modern browser.

The page loads two fonts from Google Fonts. Without an internet connection it falls back to your system fonts and works the same.



Jobs are added at the rear and removed from the front. A `head` index marks the front of the queue, so removing a job does not shift the others. Cancelling searches the waiting jobs for the matching id, which is why it takes O(n).

## Project structure

```
print-spooler.html   The whole project: page, styles and queue logic
README.md            This file
```

## Possible extensions

- **Priority queue**, so urgent jobs can go ahead of others
- **Multiple printers** taking jobs from one shared queue
- **Retry limits** for jobs that jam repeatedly
