```C
/*
 * Parent waits for a chosen child process to terminate
 * @param pid: of the child process to wait on
 * @param stat_loc: will hold returned info about terminated process
 * @param options: if 0, then default to blocking system call; otherwise specify WNOHANG for nonblocking
 */
pid_t waitpid(pid_t pid, int *stat_loc, int options)

```

## Blocking
- Blocking avoid wasted work
- Good for events that don't occur too often

## Polling
- More responsive
- "Busy-waiting" as opposed to blocking