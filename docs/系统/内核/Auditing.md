# Auditing

## Overview

sketch
- auditctl tool
- auditd daemon

types of audit events
- system call auditing
- all other types of evento

## Audit rules

basic rule
- filter/value
- filter: entry/...
  - filed/comparator/valule
- value: NEVER/ALWAYS

Add rule
- auditctl -a filter,action -F filed=value

## Implementation

### Data structure

struct task_struct
- stuct audit_context
  - enum audit_state
  - struct audit_names
  - struct audit_aux_data
  - ...

struct audit_buffer
- struct sk_buff
- struct audit_context

struct audit_rule_data
struct audit_field
struct audit_krule
struct audit_entry
- struct audit_krule

audit_add_rule

### Initialization

audit_init

### Processing requests

audit_receive -> audit_receive_skb -> audit_receive_msg

### Logging events

audit_log_start -> audit_log_format -> audit_log_end

### System call auditing

audit_alloc -> audit_syscall_entry -> audit_syscall_exit

Access vector cache auditing: avc_audit