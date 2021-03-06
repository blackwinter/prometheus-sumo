
Testing
=======

## Test specifications

Tests are defined in the ``spec`` sub-directory:

    spec/
    |-- controllers
    |-- fixtures
    |-- helpers
    |-- lib
    |-- models
    |-- shared
    |   `-- matchers
    `-- views

## Running the tests

In order to get a list of all available tests, use the command

    rake -T spec

The resulting list should contain entries like this:

    rake spec                         Run all specs in spec directory (excluding plugin specs)
    rake spec:clobber_rcov            Remove rcov products for rcov
    rake spec:controllers             Run the code examples in spec/controllers
    rake spec:db:fixtures:load        Load fixtures (from spec/fixtures) into the current environment's database.
    rake spec:doc                     Print Specdoc for all specs (excluding plugin specs)
    rake spec:helpers                 Run the code examples in spec/helpers
    rake spec:lib                     Run the code examples in spec/lib
    rake spec:models                  Run the code examples in spec/models
    rake spec:plugin_doc              Print Specdoc for all plugin examples
    rake spec:plugins                 Run the code examples in vendor/plugins (except RSpec's own)
    rake spec:plugins:rspec_on_rails  Runs the examples for rspec_on_rails
    rake spec:rcov                    Run all specs in spec directory with RCov (excluding plugin specs)
    rake spec:server:restart          reload spec_server.
    rake spec:server:start            start spec_server.
    rake spec:server:stop             stop spec_server.
    rake spec:views                   Run the code examples in spec/views

Since essentially the specs are groups into Rake tasks, running them is as
simple as e.g. 

    rake spec:models

If however you want a bit more control over the test carried out, you e.g. can
utilize the ``SPEC`` option to pass along an individual file with test instructions:

    rake spec SPEC=spec/models/image_spec.rb

Using ``SPEC_OPTS`` it is possible to pass along options e.g. to influence the
formatting of the output.

    rake spec SPEC=spec/controllers/institution_controller_spec.rb SPEC_OPTS="--format nested --color"

which will result in something like this (color missing here though):

    InstitutionController
      in general
        should redirect to login if user is not logged in
        should redirect to email confirmation if user's email is not already confirmed
        should redirect to license if the current user's license is expired
      handling GET /institution/index
        should redirect to /institution/list if user is allowed
        should redirect to /institution/show if user is not allowed to see the list
      handling GET /institution/show
        should not show the given institution if current user is not allowed (FAILED - 1)
        when allowed
          should successfully render the template
          should show the current user's institution
          should show the given institution
