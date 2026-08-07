Preparing a Release
===================

The following steps are needed to prepare a release:

1. Make sure the VERSION in ``django_redis/__init__.py`` has been updated.
2. Run ``towncrier build`` to update the ``CHANGELOG.rst`` with the
   news fragments for the release.
3. Commit the changes for steps 1 and 2.
4. Tag the commit ``v<VERSION>`` -- the same version as specified for VERSION
   in step 1, prefixed with ``v`` (for example ``v6.0.2``).
5. Push the tag. The `release action`_ builds the sdist and wheel, verifies
   that they declare ``django-redis-iplweb`` at the tagged version, and uploads
   them to `django-redis-iplweb on PyPI`_.

Authentication uses `PyPI Trusted Publishing`_ (OIDC), so no API token is
stored in this repository. PyPI is configured to trust this repository, the
``release.yml`` workflow and the ``pypi`` environment; changing any of them
means updating the publisher entry on PyPI as well.

.. _release action: https://github.com/mpasternak/django-redis-iplweb/actions/workflows/release.yml
.. _django-redis-iplweb on PyPI: https://pypi.org/project/django-redis-iplweb/
.. _PyPI Trusted Publishing: https://docs.pypi.org/trusted-publishers/
