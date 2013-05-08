#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.53)
AC_PACKAGE_VERSION(0.1.0)
AC_INIT(tls, 0.1.0, [], [])

# Checks for programs.
AC_PROG_CC
AC_PROG_MAKE_SET

if test "x$GCC" = "xyes"; then
    CFLAGS="$CFLAGS -Wall"
fi

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST

# Checks for library functions.
AC_FUNC_MALLOC
AC_HEADER_STDC

# Checks Erlang runtime and compiler
AC_ERLANG_NEED_ERL
AC_ERLANG_NEED_ERLC

# Checks and sets ERLANG_ROOT_DIR and ERLANG_LIB_DIR variable
AC_ERLANG_SUBST_ROOT_DIR
AC_ERLANG_SUBST_LIB_DIR

AC_CHECK_LIB(ssl, SSL_free, [SSL_LIB=yes], [], [])
AC_CHECK_LIB(crypto, SHA1_Init, [CRYPTO_LIB=yes], [], [])
AC_CHECK_HEADERS([openssl/ssl.h openssl/err.h openssl/sha.h], [], [], [])

if test "x$SSL_LIB" = "x"; then
   AC_MSG_ERROR([OpenSSL 'ssl' library was not found])
fi

if test "x$CRYPTO_LIB" = "x"; then
   AC_MSG_ERROR([OpenSSL 'crypto' library was not found])
fi

if test "x$HAVE_OPENSSL/SSL.H" = "x"; then
   AC_MSG_ERROR([OpenSSL header file "openssl/ssl.h" was not found])
fi

if test "x$HAVE_OPENSSL/ERR.H" = "x"; then
   AC_MSG_ERROR([OpenSSL header file "openssl/err.h" was not found])
fi

if test "x$HAVE_OPENSSL/SHA.H" = "x"; then
   AC_MSG_ERROR([OpenSSL header file "openssl/sha.h" was not found])
fi

AC_OUTPUT