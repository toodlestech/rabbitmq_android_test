lib_LTLIBRARIES = librabbitmq.la

librabbitmq_la_SOURCES = amqp_mem.c amqp_table.c amqp_connection.c amqp_socket.c amqp_debug.c amqp_api.c
nodist_librabbitmq_la_SOURCES = amqp_framing.c
include_HEADERS = amqp_framing.h amqp.h
noinst_HEADERS = amqp_private.h
BUILT_SOURCES = amqp_framing.h amqp_framing.c
CLEANFILES = amqp_framing.h amqp_framing.c
EXTRA_DIST = codegen.py

CODEGEN_PY=$(srcdir)/codegen.py

amqp_framing.h: $(AMQP_SPEC_JSON_PATH) $(CODEGEN_PY)
	PYTHONPATH=$(AMQP_CODEGEN_DIR) $(PYTHON) $(CODEGEN_PY) header $< $@

amqp_framing.c: $(AMQP_SPEC_JSON_PATH) $(CODEGEN_PY)
	PYTHONPATH=$(AMQP_CODEGEN_DIR) $(PYTHON) $(CODEGEN_PY) body $< $@
